Cesium VectorTileImageryProvider
֧��С��������geojson��shape�ļ�ʸ����̬��Ƭ��ʵ������
![](https://mikeswei.github.io/CesiumVectorTile/screenshot.jpg)
![](https://mikeswei.github.io/CesiumVectorTile/screenshot2.jpg)
![](https://mikeswei.github.io/CesiumVectorTile/screenshot3.jpg)

npm ��װ

        npm install CesiumVectorTile

ʾ����
```javascript 
        VectorTileImageryProvider = Cesium.VectorTileImageryProvider;

        viewer = new Cesium.Viewer("cesiumContainer");
        var imageryProviderViewModels = viewer.baseLayerPicker.viewModel.imageryProviderViewModels;
        viewer.baseLayerPicker.viewModel.selectedImagery = imageryProviderViewModels[imageryProviderViewModels.length - 1];
        viewer.scene.debugShowFramesPerSecond = true;
        
        var provinceLayer = null;
        var provinceProvider = new VectorTileImageryProvider({
            source: appConfig.BaseURL + "Assets/Data/json/china_province.geojson",
            defaultStyle: {
                outlineColor: "rgb(255,255,255)",
                lineWidth: 2,
                fill: false,
                tileCacheSize: 200
            },
            maximumLevel: 20,
            minimumLevel: 1,
            simplify: false
        });
        provinceProvider.readyPromise.then(function () {
            provinceLayer = viewer.imageryLayers.addImageryProvider(provinceProvider);
        });

        var worldLayer = null;
        var worldProvider = new VectorTileImageryProvider({
            source: appConfig.BaseURL + "Assets/Data/shp/world/���Ҽ򻯱߽�.shp",
            defaultStyle: {
                outlineColor: "rgb(255,0,0)",
                lineWidth: 1,
                fill: false,
                tileCacheSize: 200,
                showMaker: false,
                showCenterLabel: true,
                fontColor: "rgba(255,0,0,1)",
                labelOffsetX: -10,
                labelOffsetY: -5,
                fontSize: 13,
                fontFamily: "����",
                centerLabelPropertyName: "NAME"
            },
            maximumLevel: 20,
            minimumLevel: 1,
            simplify: false
        });
        worldProvider.readyPromise.then(function () {
            worldLayer = viewer.imageryLayers.addImageryProvider(worldProvider);
        });
```
#####  ����
* [Cesium](https://github.com/AnalyticalGraphicsInc/cesium)
* [turf](https://github.com/Turfjs/turf)
* [shpjs](https://github.com/calvinmetcalf/shapefile-js)
* [proj4js](https://github.com/proj4js/proj4js)
* [text-encoding](https://github.com/inexorabletash/text-encoding)
* [geojson-topojson](https://github.com/JeffPaine/geojson-topojson)
#####  ����
###### 2018.07.14��
* 1��֧�����°�Cesium��
* 2��֧����ע�ǵķ�ʽ��ʾ�ؼ����ԣ�������ȡ�