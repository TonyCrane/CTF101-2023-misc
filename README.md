# 2023「安全攻防实践基础」misc 部分课件

## 课程介绍
2023 年浙江大学计算机学院短学期课程综合实践 I 中「安全攻防实践基础」课程（即 AAA 战队开设的 CTF 课程）的 misc 部分。

课程主仓库在：[team-s2/summer_course_2023](https://github.com/team-s2/summer_course_2023/)，课程网站在：[courses.zjusec.com](https://courses.zjusec.com/)。

misc 部分三次课程，一次必修的 misc 基础，两次选修的 misc 专题。课程主页托管在 <https://slides.tonycrane.cc/CTF101-2023-misc/>。

## 关于 slides
### 构建与部署

<details>
<summary>原版指南</summary>

1. 安装 reveal-md
    ```sh 
    $ npm install -g reveal-md
    ```
2. 在浏览器中实时预览
    ```sh 
    $ reveal-md main.md -w
    ```
3. 构建静态文件
    ```sh 
    $ reveal-md main.md --static site --assets-dir assets
    ```
    - 生成 pdf 版：在 url 后面加上 `?print-pdf` 使用浏览器打印
4. 部署
    - 很蠢的一个实现，总之就是用 Action 把 site 文件夹中的内容复制到我的另一个私有 repo 中，然后在那个 repo 里部署 GitHub Pages
    - 构建出 site 文件夹后 commit & push，message 需要以 `[deploy]` 开头

</details>

本课程所有 slides 都使用 reveal-md，源码都在 slides/src/ 目录中，同时包含了一个简单的 Makefile 用来更方便地预览和构建。

- 实时预览
    ```sh 
    $ make         # 仅 lec0
    $ make LECNO=1 # lec1
    ```
- 单个 slides 构建
    ```sh
    $ make build         # 仅 lec0
    $ make LECNO=1 build # lec1
    ```
- 构建全部 slides
    ```sh
    $ make all
    ``` 
- 清除全部 slides
    ```sh
    $ make clean
    ```

### 用法

和 reveal-js 的快捷键一致，在页面中按下 `?` 可以查看所有快捷键。常用的：

- N / SPACE：下一页
- P / Shift SPACE：上一页
- ← / H：翻到左边页面
- → / L：翻到右边页面
- ↑ / K：翻到上边页面
- ↓ / J：翻到下边页面
- B / .：暂停（黑屏）
- F：全屏
- ESC / O：显示概览
- S：打开演讲者窗口
