MIST32 Instruction Format
==========
大きく分けて2つフォーマットがあり、O フォーマットと、I フォーマットがあります。オペランドにレジスタを取るフォーマットと、即値を取るフォーマットです。

命令によっては、O フォーマットと I フォーマットが共通で使えるものがあります。bit 20 でどちらのフォーマットを使うかを判断します。


I11
====
Immediate 11 Format

| 31 | 30…21 | 20 | 19…16 | 15…10 | 9…5 | 4…0 |
|--------|--------|--------|--------|--------|--------|--------|
| (Reserved) | Opcode | 1 | AFE | Immediate[10...5] | Operand1(Destination) | Immediate[4...0] |

I16
====
Immediate 16 Format

|31|30…21|20…10|9…5|4…0|
|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|Immediate[15...5]|Operand1(Destination)|Immediate[4...0]|


O2
====
Register Operand 2 Format

|31|30…21|20|19…16|15…10|9…5|4…0|
|--------|--------|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|0|AFE|ADV|Operand1(Destination)|Operand2|

ADV : Displacementつきアクセスの場合、この領域はDisplacementとして扱われ、その他の命令は未使用になります。

O1
====
Register Operand 1 Format

|31|30…21|20|19…16|15…10|9…5|4…0|
|--------|--------|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|0|AFE|(Reserved)|Operand1(Destination)|(Reserved)|


C
====
Control Fotmat

|31|30…21|20|19…16|15…0|
|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|0|AFE|(Reserved)|

CI16
====
Control Immediate Fotmat

|31|30…21|20|19…16|15…0|
|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|1|AFE|Immediate[15...0]|

JI16
====
Jump Immediate Format


|31|30…21|20|19…16|15…0|
|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|1|CC|Immediate[15…0]|


JO1
====
Jump Register Operand Format

|31|30…21|20|19…16|15…10|9…5|4…0|
|--------|--------|--------|--------|--------|--------|--------|
|(Reserved)|Opcode|0|CC|(Reserved)|Operand1|(Reserved)|

