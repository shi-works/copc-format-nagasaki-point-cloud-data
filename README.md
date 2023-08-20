# copc-format-nagasaki-point-cloud-data

## Public Website


## COPCの生成方法
- [pdal 2.5.2](https://pdal.io/en/latest/)

```
# OSGeo4W Shellを起動
# メタデータの確認
pdal info --metadata 01ke9821_org.las

# 座標参照系の付与
pdal translate -i 01ke9821_org.las -o 01ke9821_translated.las --writers.las.a_srs="EPSG:6669"

# メタデータの確認
pdal info --metadata 01ke9821_translated.las

# COPCへの変換
pdal translate -i 01ke9821_translated.las -o 01ke9821_translated.copc.laz --writers.copc.forward=all
```

## COPCの表示
- 以下のように直接URLを指定してアクセス
https://viewer.copc.io/?copc=https://www.example.com/xxx.copc.laz
