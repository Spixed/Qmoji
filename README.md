# Qmoji

## Introduction

Collect QQ Emojis from app QQNT for personal use. (I called it Qmoji, so Qmoji is not the official name of this series of emojis)

They're stored in `/Users/{username}/Library/Containers/com.tencent.qq/Data/Library/Application Support/QQ/global/nt_data/Emoji/emoji-resource` in macOS(I don't know where they are in other systems), then I extracted them and did a little work of sorting. 

> This repo is not affiliated with Tencent. All rights reserved.

It includes Super Qmoji and Normal Qmoji, with various file formats like `lottie.json`, `apng.png` and `thumb.png`.

## Usage

1. Fetch `mapping.json` from this repo. You can use `https://raw.githubusercontent.com/Spixed/Qmoji/refs/heads/main/mapping.json` or `https://cdn.jsdelivr.com/gh/Spixed/Qmoji@main/mapping.json` to fetch it.
2. Use `mapping.json` to check the emojiId you want to use. (to see the structure of this json in detail, read the document below)
3. Fetch the emoji files from this repo. Use `https://raw.githubusercontent.com/Spixed/Qmoji/refs/heads/main/res/{emojiId}/{thumb.png[|apng.png|(lottie.json)]}` or `https://cdn.jsdelivr.com/gh/Spixed/Qmoji@main/res/{emojiId}/{thumb.png[|apng.png|(lottie.json)]}` to fetch it.

> Of course you can fork it and change the url to your own repo. 
> Or also you can clone it to your local machine to use it locally. 

### Structure of `mapping.json`

`mapping.json` is a json file that maps the emojiId to the emoji files. The structure of this json is as follows:

```json
[
    ...
    {
        "emojiId": "(int, crucial to find resources of this emoji)",
        "describe": "/(str, emoji describe, used to describe the meaning of this emoji, while for most qmojis, we don't use it in the meanings given by QQ official)",
        "emojiType": "(int, 0 for normal qmoji which only has thumb.png, 1 for normal qmoji which has apng.png and thumb.png, and 2 for super qmoji which has lottie.json, apng.png and thumb.png)"
    },
    ...
]
```