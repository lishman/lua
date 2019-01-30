# gdal.geometry

# 构建

|Function|OverView|Parameters|Returns|
|:---|---|---|---|
|[new](new.md)|创建几何对象|<li>string : wkt <li> osr = nil|geometry|
|[new](new.md)|创建几何对象|<li>string : wkb <li> osr = nil|geometry|
|[new](new.md)|创建几何对象|<li>integer: wkbtype|geometry|

# 方法
|Function|OverView|Parameters|Returns|
|:---|---|---|---|
|[getOSR](getOSR.md)|获取投影坐标系|this|osrptr|*|
|[setOSR](setOSR.md)|设定投影坐标系|<li>this<li>osr/ostptr||*|
|[getPoint](setPoint.md)|获取坐标|this|<li>real : x<li>real : y<li> real : z|Point|
|[setPoint](setPoint.md)|设置坐标|<li>this<li>real : x<li>real : y<li> real=nil : z||Point|
|[getNumPoints](getNumPoints.md)|获取坐标数目|this|real|LineString, LinearRing||
|[getPoint](setPoint.md)|获取坐标|<li>this<li>integer : position|<li>real : x<li>real : y<li> real : z|LineString, LinearRing|
|[setNumPoints](setNumPoints.md)|设置坐标数目|<li>this<li>integer||LineString, LinearRing||
|[setPoint](setPoint.md)|设置坐标|<li>this<li>integer : position<li>real : x<li>real : y<li> real=nil : z||LineString, LinearRing|
|[asText](asText.md)|转换为WKT文本|this|string|*|
|[asWKB](asWKB.md)|转换为WKB二进制|this|string|*|
|[__tostring](asWKB.md)|转换为WKT文本|this|string|*|

# 基本函数
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|
|[type](type.md)|获取几何对象类型|type(this)|integer|*|
|[getdims](getdims.md)|获取几何最大维数|this|integer : [0:点, 1:线, 2:面]|*|
|[getName](type.md)|获取几何对象名称|getName(this)|string|*|
|[isRing](isRing.md)|是否为环对象|this|bool|*|
|[isEmpty](isEmpty.md)|是否为空对象|this|bool|*|
|[isValid](isValid.md)|是否为有效对象|this|bool|*|
|[isSimple](isSimple.md)|是否为简单对象|this|bool|*|
|[isClockwise](isClockwise.md)|是否为顺时针对象|this|bool|*|
|[empty](empty.md)|清空|this||*|
|[swapXY](swapXY.md)|交换坐标xy分量|this||*|
|[centroid](centroid.md)|获取重心|this|<li>real : x<li>real : y|*|
|[getEnvelope](getEnvelope.md)|获取矩形包围区域|this|<li>real : xmin<li>real : xmax<li>real : ymin<li>real : ymax|*|

# 转换
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|
|[reverse](reverse.md)|点序反转|this|geometry|*|
|[clone](clone.md)|复制对象|this|geometry|*|
|[boundary](boundary.md)|计算边界|this|geometry|*|
|[convexHull](convexHull.md)|计算凸包|this|geometry|*|
|[buffer](buffer.md)|计算缓冲区|<li>this<li>real : 缓冲宽度<li>integer : 直角分段|geometry|*|
|[simplify](simplify.md)|简化|<li>this<li>real : 节点最小间距|geometry|*|
|[simplifyPreserveTopology](simplifyPreserveTopology.md)|保证拓扑简化|<li>this<li>real : 节点最小间距|geometry|*|
|[polygonize](polygonize.md)|多边形化|this|geometry|*|
|[closeRings](closeRings.md)|内部所有环进行闭合|this||*|
|[transform](transform.md)|投影转换|<li>this<li>osr|geometry|*|
|[transform](transform.md)|坐标转换|<li>this<li>[x, y, z]=(x, y, z)|geometry|*|
|[combine](combine.md)|整合所有几何对象|<li>this<li>...|geometry|*|
|[extract](extract.md)|提取内部几何对象|<li>this<li>integer : 几何类型|<li>geometryptr<li>...|*|
|[meshclip](meshclip.md)|格网切割|<li>bool=(geometryptr, meshlevel, meshcode)<li>integer : 最大切割数目 <li>geometry/geometryptr<li>...|<li>geometryptr<li>...|*|

# 长度/面积/距离
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|---|
|[area](area.md)|获取面积|this|real|*|
|[length](length.md)|获取长度|this|real|*|
|[distance](distance.md)|获取对象间的距离|<li>this<li>geometry/geometryptr|real|*|
|[perimeter](perimeter.md)|获取周长|this|real|*|
|[boost_area](boost_area.md)|获取面积, 单位m<sup>2|<li>this<li>r=6370997 : 地球半径|real|wgs84|
|[sphere_area](sphere_area.md)|获取球表面积, 单位m<sup>2|<li>this<li>r=6370997 : 地球半径|real|wgs84|
|[sphere_length](sphere_length.md)|获取球表面积, 单位m|<li>this<li>r=6370997 : 地球半径|real|wgs84|
|[sphere_length](sphere_length.md)|获取两点距离, 单位m|<li>ax<li>ay<li>bx<li>by<li>r=6370997 : 地球半径|real|wgs84|
|[sphere_perimeter](sphere_perimeter.md)|获取球表周长, 单位m|<li>this<li>r=6370997 : 地球半径|real|wgs84|

# 多边形对象
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|---|
|[addRing](addRing.md)|添加环|<li>this<li>geometry/geometryptr||Polygon|
|[getExteriorRing](getExteriorRing.md)|获取外环|this|geometryptr|Polygon|
|[getNumInteriorRings](getNumInteriorRings.md)|获取内环个数|this|integer|Polygon|
|[getInteriorRing](getInteriorRing.md)|获取内环|<li>this<li>integer : 位置|geometryptr|Polygon|

# 复合对象
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|---|
|[addGeometry](addGeometry.md)|添加几何对象|<li>this<li>geometry/geometryptr||Multi*|
|[getNumGeometries](getNumGeometries.md)|获取几何对象数目|this|integer|Multi*|
|[getGeometryRef](getGeometryRef.md)|获取几何对象|<li>this<li>integer : 位置|geometryptr|Multi*|
|[removeGeometry](removeGeometry.md)|移除几何对象|<li>this<li>integer : 位置||Multi*|

# 几何运算
几何对象关系描述可参考[`wiki几何关系`](https://en.wikipedia.org/wiki/Spatial_relation)

|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|
|[equals](equals.md)|是否等价|<li>this<li>geometry/geometryptr|bool|*|
|[intersects](intersects.md)|是否相交|<li>this<li>geometry/geometryptr|bool|*|
|[disjoint](disjoint.md)|是否隔离|<li>this<li>geometry/geometryptr|bool|*|
|[touches](touches.md)|是否接触|<li>this<li>geometry/geometryptr|bool|*|
|[crosses](crosses.md)|是否跨越|<li>this<li>geometry/geometryptr|bool|*|
|[within](within.md)|是否被包含|<li>this<li>geometry/geometryptr|bool|*|
|[contains](contains.md)|是否包含|<li>this<li>geometry/geometryptr|bool|*|
|[overlaps](overlaps.md)|是否重叠|<li>this<li>geometry/geometryptr|bool|*|
|[unionCascaded](unionCascaded.md)|联合|this|geometry|*|
|[union](union.md)|A ∪ B|<li>this<li>geometry/geometryptr|geometry|*|
|[intersection](intersection.md)|A ∩ B|<li>this<li>geometry/geometryptr|geometry|*|
|[difference](difference.md)|A - B|<li>this<li>geometry/geometryptr|geometry|*|
|[symDifference](symDifference.md)|(A ∪ B) - (A ∩ B)|<li>this<li>geometry/geometryptr|geometry|*|

# gpc
> 该组函数不稳定

|Function|OverView|Parameters|Returns|
|:---|---|---|---|
|[gpc_union](gpc_union.md)|A ∪ B|<li>this<li>geometry/geometryptr|geometry|
|[gpc_intersection](gpc_intersection.md)|A ∩ B|<li>this<li>geometry/geometryptr|geometry|
|[gpc_difference](gpc_difference.md)|A - B|<li>this<li>geometry/geometryptr|geometry|
|[gpc_symdifference](gpc_symdifference.md)|(A ∪ B) - (A ∩ B)|<li>this<li>geometry/geometryptr|geometry|

# Others
|Function|OverView|Parameters|Returns|Suitable|
|:---|---|---|---|---|
|[__gc](__gc.md)|---|---|---|---|
|[__pairs](__pairs.md)|---|---|---|---|
|[next](next.md)|---|---|---|---|
|[setPoint](setPoint.md)|---|---|---|---|
|[getPoint](getPoint.md)|---|---|---|---|
|[geometry_recv](geometry_recv.md)|---|---|---|---|
|[geometry_send](geometry_send.md)|---|---|---|---|
