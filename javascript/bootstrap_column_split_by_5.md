# Split bootstrap's column by the number which is not an aliquot part of 12.

Bootstrap is well-made UI framework tool for JS.

It has `12-columns` grid system. You can easily split page for `2, 3, 4, 6, 12` (same-sized) columns.

But sometimes we want to split the page by 5 (or 7, etc...).

If you want to split by 5, just make your own css style.

```
.col-md-2\.4 {
  float: left;
  position: relative;
  width: 20%;
}
```

```
<div class="col-md-2.4">
  1
</div>
<div class="col-md-2.4">
  2
</div>
<div class="col-md-2.4">
  3
</div>
<div class="col-md-2.4">
  4
</div>
<div class="col-md-2.4">
  5
</div>
```

Mar 6, 2017 by kyuhohan
