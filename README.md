# Amusing-pick
I like centipedes

![buh](https://github.com/nicolasbaez/Amusing-pick/blob/main/xp086.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  clear();
  h = w / 2;
  for (i = w / 4; i < w * 0.75; i += 8) {
    stroke(h, h, 0);
    noFill();
    a = map(sin(map(i + k, 0, w, 0, 9)), -1, 1, w / 3, w * 0.6);
    for (j = a - w / 9; j < a + w / 9; j++) {
      point(
        j,
        map(
          cos(map(j, a - w / 9, a + w / 9, k / 9 + 3, k / 9 + 12)),
          -1,
          1,
          i - 9,
          i + 9
        )
      );
    }
    circle(a, i, 32);
  }
  if (k == 0) saveGif("xp089.gif", 666, { delay: 0, units: "frames" });
  k += 0.5;
};
