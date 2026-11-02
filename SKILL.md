---
name: geoskill-network-routing
description: 'Dijkstra/A*多约束路径规划，支持时间/距离权重和多起终点'
---

# 网络路径规划 | Network Routing

Network path planning: supports Dijkstra and A* (admissible heuristic; the scaling factor is derived automatically from the actual edge weights to guarantee optimality), multi-constraint routing weighted by distance or time, and batch planning for multiple origins and destinations.

## Core Algorithm / 核心算法

- Dijkstra shortest path
- A* (admissible heuristic)
- Distance/time multi-constraint + multi-OD

## Dependencies / 依赖

```bash
pip install numpy rasterio scipy geopandas shapely
```

## Usage / 使用方法

### Example 1 (synthetic data, offline)

```bash
python geoskill-network-routing.py --bbox 116.0 39.0 117.0 40.0 --synthetic --output-dir ./out
```

### Example 2 (specified area + quiet mode)

```bash
python geoskill-network-routing.py --bbox 121.0 31.0 122.0 32.0 --synthetic --output-dir ./out2 --quiet
```

### Example 3 (real input)

```bash
python geoskill-network-routing.py --input <your data file> --output-dir ./out3
```

### Example 4 (tiny-area boundary test)

```bash
python geoskill-network-routing.py --bbox 116.39 39.90 116.40 39.91 --synthetic --output-dir ./out4 --quiet
```

## Output / 输出

| File | Format | Description |
|---|---|---|
| `routes.geojson` | GeoTIFF/GeoJSON/JSON | Main output |
| `routing_stats.json` | GeoTIFF/GeoJSON/JSON | Main output |
| `output-manifest.json` | JSON | Run manifest |

## Data Source / 数据源 / Source

- Synthetic mode: physically consistent simulated data generated locally; no external data source.
- Real mode: reads local input files; no network requests.

## Privacy / 隐私声明 / Privacy

- Runs fully offline by default; no network requests are made.
- `--synthetic` mode reads no external data.
- All computation is performed locally; user data is never uploaded.

## License / License

MIT

---

> 中文完整版：需要时再读 [references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)，不要默认全量加载。
