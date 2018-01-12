---
title: "-Zc: トライグラフ (トライグラフの置換) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /Zc
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 739e772c87c937a552e07a32fa5bb80b1a1e2508
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (トライグラフの置換)
ときに**/Zc:trigraphs**を指定すると、コンパイラは、対応する区切り文字を使用して、トライグラフ文字シーケンスを置き換えます。 トライグラフの置換機能をオフにするには、次のように指定します。 **/Zc:trigraphs-**です。 既定では、 **/Zc:trigraphs**は無効になっています。  
  
## <a name="syntax"></a>構文  
  
```  
/Zc:trigraphs[-]  
```  
  
## <a name="remarks"></a>コメント  
 トライグラフは、2 つの連続する疑問符 ("??") と、一意の 3 番目の文字で構成されます。 たとえば、コンパイラ、"[概要] タブ="トライグラフ '#' 文字を使用しています。 トライグラフは、一部の区切り文字に対応する適切なグラフィック表示がない文字セットを含む C ソース ファイルで使用できます。  
  
 C と C++ トライグラフとトライグラフを使用する方法を示す例の一覧は、次を参照してください。[トライグラフ](../../c-language/trigraphs.md)です。  
  
## <a name="see-also"></a>参照  
 [/Zc (準拠)](../../build/reference/zc-conformance.md)   
 [トライグラフ](../../c-language/trigraphs.md)