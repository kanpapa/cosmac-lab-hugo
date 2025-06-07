---
title: COSMAC CPUについて
Subtitle: ""
date: 2000-01-01
Lastmod : 
tags: ["about"]
image : "/img/cosmac-cpu/cosmac_cdp1802ace.jpg"
Description  : "COSMAC CPUの概要です"
---

{{< figure src="/img/cosmac-cpu/cosmac_cdp1802ace.jpg" >}}

COSMAC CPUとは、1970年代半ばにRCA社が開発した高信頼性CMOS 8ビットマイクロプロセッサCDP1802です。CPUのプログラムローダーの機能により、トグルスイッチでプログラムを書き込むことができます。アセンブラの知識は必要ですが、簡単なものであれば数バイト書き込むだけで動かすことができます。

### 主な特徴

* 低消費電力(最大クロックで8mW)
* 広い電源電圧範囲(4V~6.5V)
* クロックは最大3.2MHzで下限なし
* 耐放射線
* シンプルなアーキテクチャ

### 用途

* 航空宇宙、軍用、および重要産業用装置

### CPUのピン配置

扱いやすい40P DIPです。

{{< figure src="/img/cosmac-cpu/cpu_pin.png" >}}

※intersil CDP1802 datasheetから引用

### Registers

Dレジスタは8ビットのアキュムレータです。16ビットの汎用レジスタが16個あり、どのレジスタもプログラムカウンタやインデックスレジスタにできるユニークな構成です。またQレジスタで1ビットの出力ができます。

{{< figure src="/img/cosmac-cpu/cpu_register.png" >}}

※intersil CDP1802 datasheetから引用

### Instruction set

COSMAC CPUの命令セットは１枚の表にまとめることができます。

{{< figure src="/img/cosmac-cpu/1802_instruction_matrix.gif" >}}

※The 1802 Instruction Setから引用

### Sample program

Q出力に0,1を繰り返し出力するプログラム

```
0000 7B    START SEQ
0001 7A          REQ
0002 30 00       BR START
```
