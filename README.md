# Saltline · 港区双关战役

打开 `index.html`，在标题页选择关卡。也可以运行 `python3 -m http.server 8731`，在本地浏览器打开以下地址。

| 关卡 | 入口 | 任务 |
| --- | --- | --- |
| 东码头潮位站 | http://localhost:8731/ | 以任意顺序切断四处中继，到南端船梯撤离。 |
| 北闸泵站 | http://localhost:8731/?mission=north-lock | 按 A、B、C 的顺序启动进水泵、均压阀、闸门主控，再穿过升起的闸门撤离。 |

靠近控制台、面向面板并长按 **E**。首关结算页可进入第二关。两关共用原版渲染、输入、敌人和终端交互的逻辑。作者与原始镜像说明见下方。

## 上游镜像说明 · Saltline — Fable 5.2 FPS

A small browser first-person shooter: one level in a rainy container port. Cut three uplink relays while drones ("Gulls") and robot dogs ("Hounds") hunt you.
<img width="1685" height="906" alt="image" src="https://github.com/user-attachments/assets/8dd32149-90f4-4d69-a573-4411a49a9ba9" />


## Demo
https://realcodebear.github.io/saltline-fable-5.2/

## Where it comes from

- Built by **Claude Fable 5.2**. The run was set up by Felix Rieseberg (Anthropic) and shared on X on 2026-11-09:
  https://x.com/felixrieseberg/status/2119925633564463609
- Original playable artifact: https://claude.ai/artifact/BGY1SztrAYcJQHSsnHHGmp
- Per his post: one prompt, no human feedback, about 8 hours, about 2.7M output and 445M input tokens (heavily cached), about $550 at API pricing. Models, sounds and textures are all made in code. These numbers are his own and not checked here.

All credit for the game goes to its original author. This repo is a mirror so people can run it locally. If you are the author and want it taken down, open an issue.

## What the upstream mirror changed from the artifact

The upstream mirror preserved the original game code. The claude.ai frame-runtime scripts were removed from `<head>`, and a doctype, charset and viewport tag were added so the file runs as a plain web page.

## Run it

```sh
python3 -m http.server 8731
```

Then open http://localhost:8731 and click the page to capture the mouse and start the sound.

The whole game is one file, `index.html` (~1.4 MB). It bundles three.js and loads fonts from Google Fonts. There are no other outside assets.
