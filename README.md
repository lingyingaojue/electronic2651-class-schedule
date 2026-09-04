# 电子2651 班级课表 · Electronic 2651 Class Timetable

2026-2027-1 学年学期班级课表（交互式单文件网页）。

纯原生 HTML / CSS / JavaScript，**零依赖、零构建**，一个 `index.html` 即可运行。

![status](https://img.shields.io/badge/tech-html%2Fcss%2Fjs-blue) ![license](https://img.shields.io/badge/license-MIT-green)

---

## 预览地址（GitHub Pages）

上传后开启 GitHub Pages（见下文「部署」），站点地址为：

```
https://<你的GitHub用户名>.github.io/electronic2651-class-schedule/
```

本地预览：直接双击 `index.html`，或在项目目录运行

```bash
python -m http.server 8080     # 或 npx serve 等任意静态服务器
# 浏览器打开 http://localhost:8080
```

---

## 页面内容

- 班级：**电子2651**（44 人）｜ 班主任：房厦 ｜ 学制：五年一贯制
- 周次视窗：第 2-5 周；时段 08:40–10:00 / 10:20–11:40 / 13:20–14:40 / 15:00–16:20
- 学期备注：第 11-14 周为实训周；理论课教室第 2-14 周在辑志216，第 15-18 周在辑志112
- 课程：语文A-1-5 / 数学A-1-5 / 英语A-1-5 / 历史A-1-5 / 体育A-1-5 / 机械与电气制图 / 电工基础（五年一贯制-1）/ 信息技术（五年一贯制-1）

> 排课数据依据教务系统截图（OCR）识读整理，最终以教务系统为准。

## 功能特性

- 🌫️ 玻璃拟态（Glassmorphism）UI + 深色渐变动态背景
- ✨ 交互动效：光标跟随光效、呼吸光晕、点击光波、悬停上浮（课程卡 / 列表头 / 节次格 / 空课格 / 信息卡 / 弹窗内卡片等）
- 🎞️ 入场动画与过渡（支持 `prefers-reduced-motion` 降级）
- 🔍 课程图例筛选、星期列聚焦、组合过滤
- ⏰ 跟随当前时间高亮「今日列 + 当前节次」，并区分 课前/课间/午休/放学 文案
- 🪟 课程详情弹窗（教师/班主任/周分布/上课安排）
- ♿ 键盘可达与读屏支持：弹窗焦点陷阱与还原、`aria-pressed/live/labelledby`、过滤态 `tabindex` 治理
- 📱 响应式：五列等宽铺满，窄屏横向滑动 + 粘性节次列

## 数据维护

课程与课表数据集中在 `index.html` 内脚本顶部的常量区：

| 常量 | 含义 |
| --- | --- |
| `COURSES` | 课程元信息（主题色 / 类别 / 任课教师） |
| `GRID` | 课表矩阵（星期 × 节次行 → 课程 / 教室） |
| `DAYS` / `SLOTS` | 星期列与节次时段 |
| `WEEKS` | 排课视窗周次 |

换学期/换课程时改常量即可，统计（门数 / 每周课时）会自动重算。

## 部署（GitHub Pages）

1. 新建公开仓库 `electronic2651-class-schedule`，把本目录文件推上去（`main` 分支）；
2. 仓库 **Settings → Pages → Source** 选择 `Deploy from a branch`，分支选 `main`，目录 `/ (root)`，保存；
3. 约 1 分钟后即可访问：

```
https://<你的GitHub用户名>.github.io/electronic2651-class-schedule/
```

## 从零推送的命令（供参考）

```bash
git init
git add index.html README.md LICENSE .gitignore
git commit -m "feat: 电子2651 班级课表（2026-2027-1）"
git branch -M main
git remote add origin https://github.com/<你的用户名>/electronic2651-class-schedule.git
git push -u origin main
```

## 许可证

[MIT](./LICENSE)
