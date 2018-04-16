---
title: "セグメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 253c3b389bd0411e6b5096e914b6a844c8f40805
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2018
---
# <a name="segment"></a>SEGMENT
呼ばれるプログラム セグメントを定義*名前*セグメント属性を持つ  
  
## <a name="syntax"></a>構文  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>パラメーター  
 *align*  
 メモリ アドレスの範囲のセグメントの開始アドレスを選択できます。 配置の種類は、次のいずれかを指定できます。  
  
|アラインメントの種類|開始アドレス|  
|----------------|----------------------|  
|**BYTE**|[次へ] の使用可能なバイトのアドレス。|  
|**WORD**|次に使用可能なワード アドレス (ワードあたり 2 バイト)。|  
|**DWORD**|次に利用可能なダブルワード アドレス (ダブル ワードあたり 4 バイト)。|  
|**PARA**|次に使用可能な段落アドレス (1 つの段落は 16 バイト)。|  
|**PAGE**|次に利用できるページ アドレス (1 ページあたり 256 バイト)。|  
|**ALIGN**(*n*)|[次へ] 使用可能な*n*番目のバイトのアドレス。 詳細については「解説」セクションを参照してください。|  
  
 このパラメーターが指定されていない場合**PARA**は既定で使用します。  
  
 *combine*  
 **パブリック**、**スタック**、**共通**、**メモリ**、**で * * * アドレス*、**プライベート**  
  
 *use*  
 **USE16**、 **USE32**、**フラット**  
  
 `characteristics`  
 **INFO**、**読み取り**、**書き込み**、 **EXECUTE**、 **SHARED**、 **NOPAGE**、 **NOCACHE**、および**破棄**  
  
 これらはサポートされて COFF のみおり、COFF セクション名の特性と同様に対応している (たとえば、 **SHARED** IMAGE_SCN_MEM_SHARED に対応しています)。 読み取りでは、IMAGE_SCN_MEM_READ フラグを設定します。 不使用の READONLY フラグには、IMG_SCN_MEM_WRITE フラグをクリアするセクションが原因です。 存在する場合`characteristics`が既定の特性は使用されず、プログラマが指定したフラグのみが有効に設定します。  
  
 `ALIAS(` `string` `)`  
 この文字列は、生成された COFF オブジェクト内のセクション名として使用されます。  異なる MASM セグメント名では、同じ外部名を複数のセクションを作成します。  
  
 サポートされていません。 **/omf**です。  
  
 `class`  
 セグメントを結合し、アセンブルされたファイルの順序付けする方法を指定します。 一般的な値は、 `'DATA'`、 `'CODE'`、`'CONST'`と `'STACK'`  
  
## <a name="remarks"></a>コメント  
 `ALIGN(n)`、`n`任意の 1 から 8192 2 の累乗をする可能性があります。 でサポートされていません**/omf**です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)