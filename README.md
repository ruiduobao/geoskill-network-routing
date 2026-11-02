# Network Routing (geoskill-network-routing)

> Dijkstra/A* multi-constraint path planning with time/distance weights and multiple origins and destinations

---

## 1. Overview

Network path planning: supports Dijkstra and A* (admissible heuristic; the scaling factor is automatically derived from the actual edge weights to guarantee optimality), multi-constraint paths weighted by distance or time, and batch planning of multiple origin-destination pairs.

## 3. Quick Start

```bash
pip install -r requirements.txt
python geoskill-network-routing.py --bbox 116 39 117 40 --synthetic --output-dir ./out
```

## 4. CLI Parameters

Run `python <skill>.py --help` for the full list. Common parameters:

| Parameter | Type | Description |
|---|---|---|
| `--bbox` | `float[4]` | WGS84 bounding box `min_lon min_lat max_lon max_lat` |
| `--input` | `path` | Local input file (GeoJSON/GeoTIFF/etc.) |
| `--output-dir` | `path` | Output directory (default `./output`) |
| `--synthetic` | `flag` | Use synthetic data instead of real input |
| `--quiet` | `flag` | Suppress non-essential stdout |

## 5. Input / Output

| File | Format | Description |
|---|---|---|
| `routes.geojson` | GeoTIFF/GeoJSON/JSON | Primary output |
| `routing_stats.json` | GeoTIFF/GeoJSON/JSON | Primary output |
| `output-manifest.json` | JSON | Run manifest |


## 6. Technical Principle

- Dijkstra shortest path
- A* (admissible heuristic)
- Distance/time multi-constraint + multi-OD

## 8. License

MIT License. See [`LICENSE`](./LICENSE) for full text.

---

> 中文完整版：[references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)
