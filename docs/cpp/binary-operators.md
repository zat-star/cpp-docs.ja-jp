---
title: "二項演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15c52d48359210a21b23caa72afee7e2a3bcd8cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="binary-operators"></a>二項演算子
次の表は、オーバーロードできる演算子の一覧です。  
  
### <a name="redefinable-binary-operators"></a>再定義可能な二項演算子  
  
|演算子|name|  
|--------------|----------|  
|**、**|コンマ|  
|`!=`|非等値|  
|`%`|剰余|  
|`%=`|剰余/代入|  
|**&**|ビットごとの AND|  
|**&&**|論理 AND|  
|**&=**|ビットごとの AND/代入|  
|**\***|乗算|  
|**\*=**|乗算/代入|  
|**+**|加算|  
|`+=`|加算/代入|  
|**-**|減算|  
|**-=**|減算/代入|  
|**->**|メンバー選択|  
|**->\***|メンバーへのポインター選択|  
|**/**|除算記号|  
|`/=`|除算/代入|  
|**<**|より小さい|  
|**<<**|左シフト|  
|**<<=**|左シフト/代入|  
|**<=**|次の値以下|  
|**=**|代入|  
|`==`|等価比較|  
|**>**|次の値より大きい|  
|**>=**|次の値以上|  
|**>>**|右シフト|  
|**>>=**|右シフト/代入|  
|**^**|排他的 OR|  
|`^=`|排他的 OR/代入|  
|**&#124;**|ビットごとの包括的 OR|  
|`&#124;=`|ビットごとの包括的 OR/代入|  
|`&#124;&#124;`|論理 OR|  
  
 二項演算子関数を非静的メンバーとして宣言するには、次の形式で宣言する必要があります。  
  
 *ret 型***演算子**`op`**(** `arg` **)**  
  
 ここで*ret 型*戻り値の型は、`op`は前の表に示す演算子の 1 つと`arg`は任意の型の引数です。  
  
 二項演算子関数をグローバル関数として宣言するには、次の形式で宣言する必要があります。  
  
 *ret 型***演算子**`op`**(** `arg1` **、** `arg2` **)**  
  
 ここで*ret 型*と`op`メンバー演算子関数を説明したとおりと`arg1`と`arg2`引数します。 少なくとも 1 つの引数がクラス型である必要があります。  
  
> [!NOTE]
>  二項演算子の戻り値の型に制限はありません。ただし、ほとんどのユーザー定義の二項演算子は、クラス型かクラス型への参照を返します。  
  
## <a name="see-also"></a>参照  
 [演算子のオーバーロード](../cpp/operator-overloading.md)