---
title: "最適化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, optimize
- optimize pragma
ms.assetid: cb13c1cc-186a-45bc-bee7-95a8de7381cc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae1988292b1f6dfa35f4cb77d145641528ed827f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="optimize"></a>optimize
実行する最適化を関数ごとに指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
#pragma optimize( "[optimization-list]", {on | off} )  
```  
  
## <a name="remarks"></a>コメント  
 **最適化**プラグマは関数の外に置く必要があり、、プラグマが発生した後に定義されている最初の関数で有効になります。 **で**と**オフ**引数で指定されたオプションを有効にする、*最適化リスト*オンまたはオフします。  
  
 *最適化リスト*次の表に示されているパラメーターの 0 個以上にすることができます。  
  
### <a name="parameters-of-the-optimize-pragma"></a>optimize プラグマのパラメーター  
  
|パラメーター|最適化の種類|  
|--------------------|--------------------------|  
|**g**|グローバル最適化を有効にします。|  
|**s**または**t**|マシン語コードの省略シーケンスまたは高速シーケンスを指定します。|  
|**y**|プログラム スタックにフレーム ポインターを生成します。|  
  
 これらで使用される同じ文字、 [/O](../build/reference/o-options-optimize-code.md)コンパイラ オプション。 たとえば、次のプラグマと同じ、 **/Os**コンパイラ オプション。  
  
```  
#pragma optimize( "ts", on )  
```  
  
 使用して、**最適化**プラグマは、空の文字列 (**""**) ディレクティブの特殊な形式です。  
  
 使用する場合、**オフ**パラメーター、オフ、このトピックの前の表で示した最適化なります。  
  
 使用すると、**で**パラメーター、最適化にリセットで指定した、 [/O](../build/reference/o-options-optimize-code.md)コンパイラ オプション。  
  
```  
#pragma optimize( "", off )  
.  
.  
.  
#pragma optimize( "", on )   
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)