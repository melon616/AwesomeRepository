OpenStreetMap
# 1. Introduction
可以下载数据从[Geofabrik](https://download.geofabrik.de/)

# 2. Osmium
Osmium是一个处理OpenStreetMap数据（.osm,.osm.pbf,.o5m格式）的高效、强大的命令行工具，基于Libosmium C++库实现。它专注于速度与灵活性、适用于提取、转换、过滤合并、压缩osm数据  

```shell
# Install for Linux(Ubuntu)
sudo apt-get install osmium-tool

# Install for Mac
brew install osmium-tool

# 查看文件基本信息
osmium fileinfo {}.osm.pbf

# 查看文件内容
osmium show {}.osm.pbf

# 裁剪指定区域内容
osmium extract -b left-bottom-coordinate,right-top-coordinate {}.osm.pbf -o {}.osm.pbf

# 提取特定对象内容
osmium tags-filter {}.osm.pbf nwr/highway -o {}.osm.pbf

# 转换为其他格式文件
osmium export {}.osm.pbf -o {}.geojson

```
# 3. Reference  
   * [Osmium Tool Manual](https://osmcode.org/osmium-tool/manual.html)
