# Photo_Wall
恋爱照片墙网站模板，Love photo wall website template

## Introduction

**English Introduction:**

This is a website template that you can store your love story photos, and you can give it as a gift to your lover, or share your love story with more people. You can click [here](https://siyuanli.tech/Photo_Wall/) to see the website demo. With this template, you can make your own website in **less than 10 minutes**.

The website is built using HTML, CSS, and JavaScript. It is responsive and works well on both desktop and mobile devices.Feel free to fork this repository and modify it to suit your needs! If you're looking to build your own love story website, this is a great place to start.

Following I will introduce the features of the website and how to create your own one from zero, both in **English and Chinese**.

**Chinese Introduction:**

这是一个网站模板，你可以存储和展示你的爱情照片。你可以把它作为一份特别的礼物送给爱人，或者分享你的爱情故事，让更多人见证你们的美好时刻。点击 [这里](https://siyuanli.tech/Photo_Wall/) 查看网站演示。使用这个模板，你可以在 **不到 10 分钟** 内轻松搭建属于自己的爱情照片网站。

该网站基于 HTML、CSS 和 JavaScript 开发，具备响应式设计，无论在桌面端还是移动端都能流畅运行。你可以自由 fork 这个仓库，并根据自己的需求进行个性化修改。如果你正在寻找一个简单又优雅的方式来展示你的爱情故事，这个模板将是一个完美的起点。

接下来，我将介绍网站的主要功能，以及如何从零开始创建你的专属爱情故事网站，包括 **英文和中文** 。

## Features:

1. **爱心轨迹**：鼠标移动时，会有爱心轨迹。同时界面底部也会始终浮出颜色更淡的爱心图案，增加浪漫氛围的同时避免颜色太鲜艳导致俗气。 

<p align="center">
    <img src="readme_img/GIF_1.gif" alt="GIF" width="80%"/>
</p>

2. **点击大图** ：点击照片后，可以查看大图，方便查看细节，并且会显示拍摄时间（如果照片信息中包含）。也可以点击esc键或者点击X号关闭大图。（加载速度受网络影响较大）

3. **切换图片** ：点击左右箭头或者键盘上下左右键可以切换图片，方便查看前后照片。

<p align="center">
    <img src="readme_img/GIF_2.gif" alt="GIF" width="80%"/>
</p>

4. **图片顺序**：在预处理时，所有的图片都会按照拍摄时间倒叙（默认）排列，最新的照片会显示在最前面。也可以自定义展示顺序。实现方式在技术细节部分。

5. **手机支持**：网站支持手机端访问，可以在手机上查看照片。

<p align="center">
    <img src="readme_img/GIF_3.gif" alt="GIF" width="30%"/>
</p>

## How to Use:
It's very easy to use this template to create your own website. Just follow the steps below:

1. **Fork this repository and Clone it to your local machine**
   1. Click the **Fork** button in the upper right corner of this repository.
   2. Delete the `images` folder, because its too big to download.
   3. Clone the repository to your local machine or download the zip file.
2. **Change your own information**:
    - **Photos**: Recreate the `images` folder and put your photos in it. Most formats of photos are supported.
    - **information**: Change the information in `index.html` at the `<!--**Name**-->`, `<!--**Birthday**-->` and `<!--**Love date**-->` places.
3. **Preprocess step 1: Rename the photos**
   - Run `step1_rename.py` to rename the photos. This script will rename all the photos in the `images` folder according to the shooting time.
4. **Preprocess step 2: Create thumbnails**: 
   - Run `step2_thumbnail.py` to create thumbnails for all the photos. This script will create thumbnails for all the photos in the `images` folder.
5. **Deploy Your Website**
   1. After finishing your edits and committing your changes, go to the GitHub repository page and click the **Settings** tab at the top.
   2. In the left-hand menu, find and click **Pages**.
   3. In the **Branch** section, change the option from **None** to the `main` branch and save.
   4. Wait a few seconds to a few minutes. After refreshing the **Pages** settings page, you'll see a URL at the top. This is the link to your newly created website.


## Technical Details:

1. **分批加载** ：照片采用分批加载的方式，每次加载 `10` 张，避免一张一张加载导致加载速度缓慢，也避免大批量加载导致刷新过慢。
2. **滚动加载** ：当滚动到距离页面底部 `1000px` 时，自动加载下一批照片。
3. **首次加载** ：首次加载时，加载 `5` 批照片，后续再根据滚动加载规则加载。
4. **缩略图** ：每张照片都有对应的缩略图，点击缩略图后再加载大图，节省加载时间和网络带宽占用。（如果某张图片没有缩略图，会自动加载原图）
5. **图片顺序** ：`step1_rename.py`中通过读取图片的 `exif` 信息，获取拍摄时间，然后按照拍摄时间排列。如果图片没有 `exif` 信息，会按照文件名排列。在网页展示时只会根据文件名进行顺序读取，因此也可以自行以其他规则命名文件。此外，本文件还将所有其他类型图片都转成jpg格式保存。
- P.S. 技术细节中的所有的数字都可以在 `script.js` 中根据需要进行修改。


图标来自[favicon.io](https://favicon.io/)