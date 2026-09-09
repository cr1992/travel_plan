# travel_plan

我自己的行程存档。每趟旅行一个 HTML，`index.html` 自动把它们列成登机牌首页。

页面在 [cr1992.github.io/travel_plan](https://cr1992.github.io/travel_plan/)。

模板和脚本在隔壁 [travel-itinerary-kit](https://github.com/cr1992/travel-itinerary-kit)。

## 加一趟行程

```bash
cp ../travel-itinerary-kit/assets/itinerary.template.html ./某地行程.html
# 改文件开头的 TRIP 对象
python3 ../travel-itinerary-kit/scripts/build_manifest.py --root . \
  --name "Travel Plan" --url https://github.com/cr1992/travel_plan
```

首页读 `manifest.json`，所以**加完行程一定要重跑这条命令**，否则新行程不会出现在首页上。

导出离线版（飞机上、没网时用）：

```bash
python3 ../travel-itinerary-kit/scripts/build_pdf.py 某地行程.html 某地行程.pdf
python3 ../travel-itinerary-kit/scripts/build_pdf.py 某地行程.html --html-out 某地行程.offline.html
```

## 这是个公开仓库

已走完的行程直接放没问题——日期成了历史，没什么可利用的。

**但未来的行程别直接 push。** 一份还没出发的行程等于写明了哪几天家里没人、这几天睡在哪。
真要提前放上来，先按 kit README「先去隐私，再公开」那节处理：日期换成 `Day 1 · 周五`，
去掉航班时刻和住宿名称地址。
