---
title: "/DISASM |Microsoft ドキュメント"
ms.date: 1/17/2018
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /disasm
dev_langs:
- C++
helpviewer_keywords:
- -DISASM dumpbin option
- DISASM dumpbin option
- /DISASM dumpbin option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d448b92c3436f3d2875bd8d9b8e0af6a7149e065
ms.sourcegitcommit: ff9bf140b6874bc08718674c07312ecb5f996463
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2018
---
# <a name="disasm"></a>/DISASM

コードのセクションでは、DUMPBIN 出力での逆アセンブルを印刷します。

## <a name="syntax"></a>構文

> **/DISASM**{**:**\[**BYTES**|**NOBYTES**]}  

### <a name="arguments"></a>引数

**BYTES**  
逆アセンブルの出力に、解釈されたオペコードと引数と共に命令のバイトが含まれます。 これは、既定の設定です。

**NOBYTES**  
命令のバイトを逆アセンブルの出力に含まれません。

## <a name="remarks"></a>コメント

**/DISASM**オプションは、ファイルのセクションではコードの逆アセンブルを表示します。 ファイルに存在する場合は、デバッグ シンボルを使用します。

**/DISASM**ネイティブな非マネージ イメージにのみ使用する必要があります。 マネージ コードと同等のツールは[ILDASM](/dotnet/framework/tools/ildasm-exe-il-disassembler)です。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションは、によって生成されたファイルで使用できるよう、 [/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)  
