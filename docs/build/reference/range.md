---
title: "-範囲は |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1ccca814a388a458513773247f79cecf87fcdeae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="range"></a>/RANGE
Dumpbin/RAWDATA または/DISASM などその他の dumpbin オプションと共に使用する場合の出力を変更します。  
  
## <a name="syntax"></a>構文  
  
```  
/RANGE:vaMin[,vaMax]  
```  
  
## <a name="flags"></a>フラグ  
 **vaMin**  
 Dumpbin 操作を開始する仮想アドレス。  
  
 **vaMax** (省略可能)  
 Dumpbin 操作を終了する仮想アドレス。 指定しない場合、dumpbin は、ファイルの末尾に移動します。  
  
## <a name="remarks"></a>コメント  
 イメージの仮想アドレスを表示するには、(RVA + ベース)、画像のマップ ファイルを使用して、 **/DISASM**または**/HEADERS** dumpbin、または Visual Studio デバッガーで逆アセンブル ウィンドウのオプションです。  
  
## <a name="example"></a>例  
 この例では**範囲/**の表示を変更するために使用、 **/disasm**オプション。 この例では、開始値が 10 進数として表され、終了値は 16 進数として指定します。  
  
```  
dumpbin /disasm /range:4219334,0x004061CD t.exe  
```  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)