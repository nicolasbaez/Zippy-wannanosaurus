# Zippy-wannanosaurus
You're going to fall into my web

![buh](https://github.com/nicolasbaez/Zippy-wannanosaurus/blob/main/xp083.gif)
```javascript
setup = (_) => createCanvas((w = 500), w);
k = 0;
draw = (_) => {
  h = w / 2;
  r = noise(k) * 99;
  stroke(h);
  clear();
  noFill();
  beginShape();
  for (i = noise(k * 0.05); i <= 48 * PI; i += PI / 6) {
    x = r * cos(i) + h;
    y = r * sin(i) + h;
    a = w * cos(i) + h;
    b = w * sin(i) + h;
    line(x, y, a, b);
    vertex(x, y);
    r += noise(x / 9, y / 9, k);
  }
  endShape();
  if (k == 0) saveGif("xp083.gif", 1000, { delay: 0, units: "frames" });
  k += 0.01;
};
