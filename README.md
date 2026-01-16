# SRAM Verification: Multi-layer and Single-layer Benchmark Instances

This repository hosts the instance data used in our paper: **Sunkanghong Wang, Qingsheng Qiu, Hao Zhang, Lijun Wei, and Qiang Liu (2025) An Efficient Algorithm for Exact SRAM Verification via Novel Pattern Matching Techniques. *IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems*.**

If you have any questions, please feel free to reach out to **[wskh0929@gmail.com](mailto:wskh0929@gmail.com)**

The formats of multi-layer and single-layer instances are described below. In all files, each polygon is written on one line as a comma-separated list of vertices:

```
(x1,y1),(x2,y2),...,(xn,yn)
```

## Multi-layer Instances

```shell
├── Multi-layer-Instances
│   ├── Hidden
│   │   ├── hidden_layout.txt
│   │   └── hidden_patterns.txt
│   ├── Large
│   │   ├── large_layout.txt
│   │   └── large_patterns.txt
│   ├── Open-Source
│   │   ├── cell_1rw_pattern.txt
│   │   └── sram_32_1024_sky130A_layout.txt
│   └── Small
│       ├── small_layout.txt
│       └── small_patterns.txt
```

### Layout TXT format

The layout file is organized by layers:

- A layer header line:

```
layer<l>:
```

- Followed by **zero or more polygon lines** until the next `layer<l>:` header or EOF

**Layout coordinates** are given in the layout’s coordinate system (they may be large or negative).

### Pattern TXT format

The pattern file may contain **multiple patterns**, each starting with:

```
pattern<i>:
```

Inside each `pattern<i>:` block:

- Layer sections:

```
layer1:
<polygon lines>
layer2:
<polygon lines>
...
```

- A key area marker section:

```
marker:
(x1,y1),(x2,y2),(x3,y3),(x4,y4)
```

The marker is a rectangle representing the key area.

**Pattern coordinates** are specified **relative to the bottom-left corner of the key area (taken as the origin)**.

## Single-layer Instances

```shell
├── Single-layer-Instances
│   ├── Layout.txt
│   └── Patterns
│       ├── I.txt
│       ├── Ind1.txt
│       ├── Ind2.txt
│       ├── Mountain.txt
│       ├── S.txt
│       ├── Stair1.txt
│       └── Stair2.txt
```

### Single-layer Layout TXT format

The single-layer layout file contains the **layout polygons on one layer**. Hence, the file is simply a **list of polygon lines**.

### Single-layer Pattern TXT format

The single-layer pattern file contains **one pattern** on a **single layer**. It is organized into two sections:

- A **pattern geometry** section:

```
pattern:
<polygon lines>
```

- A **key area marker** section:

```
marker:
(x1,y1),(x2,y2),(x3,y3),(x4,y4)
```