## 千葉市の行政区域を表現したGEOJSON

千葉市６区の行政区域をGEOJSONファイルにまとめました。
- [千葉市全域](https://github.com/codeforchiba/chibacity_geojson/blob/master/chibacity.geojson)
- [中央区](https://github.com/codeforchiba/chibacity_geojson/blob/master/chuo.geojson)
- [花見川区](https://github.com/codeforchiba/chibacity_geojson/blob/master/hanamigawa.geojson)
- [美浜区](https://github.com/codeforchiba/chibacity_geojson/blob/master/mihama.geojson)
- [稲毛区](https://github.com/codeforchiba/chibacity_geojson/blob/master/inage.geojson)
- [緑区](https://github.com/codeforchiba/chibacity_geojson/blob/master/midori.geojson)
- [若葉区](https://github.com/codeforchiba/chibacity_geojson/blob/master/wakaba.geojson)

### オリジナルデータ

国土数値情報の行政区域は６区レベルまでしかデータがないため、e-Statの国勢調査データに付随したshapeファイルを利用した。

2015/07/23補足：[位置参照情報ダウンロードサービス](http://nlftp.mlit.go.jp/cgi-bin/isj/dls/_choose_method.cgi)のデータが使えるかも

### GeoJSOファイルの作成方法

1. [e-Stat統計表検索（ダウンロード用）](http://e-stat.go.jp/SG2/eStatGIS/page/download.html)サイトで、「Step1:国勢調査」＞「平成22年度国勢調査（小地域）2010/10/01」を選択
2. 「Step2:統計表を選択」＞「男女別人口総数及び世帯総数」を選択して、「統計表各種データダウンロードへ」をクリック
3. 次ページの「Step3:地域選択」で千葉県の６区を選択し、検索ボタンをクリック
4. 「Step4:データダウンロード」に検索結果が表示されるため、境界データ画面の「世界測地系緯度経度・Shape形式」で６区のデータをダウンロード
5. ダウンロードした６つのzipファイルを解凍するとshapeファイルがあるため、それらをQGISで読み込む
6. [リンク先](http://qiita.com/mima_ita/items/5371b02fc5674809ff39)等を参考に、それぞれGeoJSONファイルに変換。ここでは不必要なデータ項目は削除してGeoJSON化した。また、shapeファイルはShift_JIS、出力するGeoJSONファイルはUTF-8に設定することに注意。
7. 生成したGeoJSONファイルから項目名がcrsの行を削除。crsはGithubが対応しておらず、地図表示されないための処置。
8. 千葉市全域のGeoJSONファイルは６区ファイルをマージして生成した。

以上
