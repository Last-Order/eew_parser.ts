# eew_parser.ts
TypeScript 紧急地震速报(緊急地震速報)电文解析器。单元测试覆盖。PLUM法支持。

## 使用
```typescript
var test = new EEWParser(`37 03 00 170228165003 C11
170228164901
ND20170228164912 NCN913 JD////////////// JN///
289 N375 E1414 050 61 04 RK66554 RT10/// RC0////
EBI 251 S0404 ////// 01 250 S0404 ////// 01 221 S0404 ////// 01
220 S0404 ////// 01 222 S0404 ////// 01 242 S0404 ////// 01
300 S0403 ////// 01 252 S0403 ////// 01
9999=`)
```

## 参考
* 解析方法来自: [eew_parser](https://github.com/mmasaki/eew_parser)
* [高度利用者向け緊急地震速報コード電文フォーマット - 緊急地震速報メモ](http://eew.mizar.jp/excodeformat)
* 配信資料に関する技術情報 第 476 号 - https://www.data.jma.go.jp/add/suishin/jyouhou/pdf/476.pdf


## 附录

### 緊急地震速報（予報）电文格式

```
「aa bb nn yiyimimididihihimimisisi Cnf yoyomomododohohomomososo NDnnnnnnnnnnnnnn
NCNann JDnnnnnnnnnnnnnn JNnnn kkk nddd edddd hhh mm ss RKn1n2n3n4n5
RTn1n2n3n4n5 RCn1n2n3n4n5 {EBI [{fff Se1e2e3e4 hhmmss y1y2}…]}
{ECI [{fffff Se1e2e3e4 hhmmss y1y2}…]} {EII [{fffffff Se1e2e3e4 hhmmss y1y2}…]}
9999=」
```

### 緊急地震速報（警報）电文格式

```
「aa bb nn yiyimimididihihimimisisi Cnf
yoyomomododohohomomososo
NDnnnnnnnnnnnnnn NCPNnn
cccc nddd edddd hhh
PRCn1n2n3n4n5
CAI {[aaaa]･･･}
CPI {[pppp]･･･}
CBI {[bbb]･･･}
PAI {[aaaa]･･･}
PPI {[pppp]･･･}
PBI {[bbb]･･･}
NCP
NDnnnnnnnnnnnnnn NCNann JDnnnnnnnnnnnnnn JNnnn
kkk nddd edddd hhh mm ss RKn1n2n3n4n5 RTn1n2n3n4n5 RCn1n2n3n4n5
EBI [{fff Se1e2e3e4 hhmmss y1y2}…]
9999=」
```
