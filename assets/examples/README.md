# XXD Shop 007 样张

每张都是本编号按 `references/sample-workflow.md` 一次生成、目视通过的原图，像素未改，只清理了元数据。商品是虚构的演示品牌，画面上的价格、规格等数字都是演示设定。

| 文件 | 用途 | 实际像素 | 输入 | 文字方式 | visual_review |
|---|---|---|---|---|---|
| `c01-category-3x4-1086x1448.png` | 详情页结构说明 | 1086x1448 | 商品图 `product-nuandao-robot.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `c02-category-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-nuandao-toothbrush.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `c03-category-16x9-1672x941.png` | 参数页横版 | 1672x941 | 商品图 `product-sc-keyboard.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `c04-category-4x5-1122x1402.png` | 详情页 | 1122x1402 | 商品图 `product-nuandao-lamp-desk.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `c05-category-1x1-1254x1254.png` | 详情页结构说明 | 1254x1254 | 商品图 `product-sc-powerbank.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `c06-category-9x16-941x1672.png` | 竖屏 | 941x1672 | 商品图 `product-sc-watch.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `p01-set-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-nuandao-fryer.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `p02-set-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-nuandao-fryer.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `p03-set-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-nuandao-fryer.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |
| `s01-size-1x1-1254x1254.png` | 详情页结构说明 | 1254x1254 | 商品图 `product-sc-headphones.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `s02-size-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-sc-headphones.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `s03-size-9x16-941x1672.png` | 竖屏 | 941x1672 | 商品图 `product-sc-headphones.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `s04-size-16x9-1672x941.png` | 参数页横版 | 1672x941 | 商品图 `product-sc-headphones.jpg`、Logo `logo-shengchuan.png` | prompt zh-CN | passed |
| `s08-category-3x4-1086x1448.png` | 详情页 | 1086x1448 | 商品图 `product-nuandao-dryer-black.jpg`、Logo `logo-nuandao.png` | prompt zh-CN | passed |

## 输入素材

`sources/` 里是生成时交给本编号的输入缩样，模拟商家手里的素材：带包装与 Logo 的商品图、品牌 Logo，个别为原图。
演示品牌、Logo 和商品图由本项目生成；其中以 Unsplash 照片为底的，署名如下，适用 [Unsplash License](https://unsplash.com/license)，**不属于**本仓库的 PolyForm Noncommercial 授权范围。

| 输入 | 说明 · 来源 |
|---|---|
| `sources/logo-nuandao.png` | 演示品牌 Logo，本项目生成 |
| `sources/logo-shengchuan.png` | 演示品牌 Logo，本项目生成 |
| `sources/product-nuandao-dryer-black.jpg` | 演示商品图，本项目生成；底图 [O4rT7zAi4ro](https://unsplash.com/photos/O4rT7zAi4ro) · @theshubhamdhage |
| `sources/product-nuandao-fryer.jpg` | 演示商品图，本项目生成 |
| `sources/product-nuandao-lamp-desk.jpg` | 演示商品图，本项目生成；底图 [CpF8oOfwuoY](https://unsplash.com/photos/CpF8oOfwuoY) · @anniespratt |
| `sources/product-nuandao-robot.jpg` | 演示商品图，本项目生成 |
| `sources/product-nuandao-toothbrush.jpg` | 演示商品图，本项目生成 |
| `sources/product-sc-headphones.jpg` | 演示商品图，本项目生成；底图 [dBwadhWa-lI](https://unsplash.com/photos/dBwadhWa-lI) · @cdx2 |
| `sources/product-sc-keyboard.jpg` | 演示商品图，本项目生成 |
| `sources/product-sc-powerbank.jpg` | 演示商品图，本项目生成 |
| `sources/product-sc-watch.jpg` | 演示商品图，本项目生成 |
