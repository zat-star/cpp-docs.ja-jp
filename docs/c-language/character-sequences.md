---
title: "文字シーケンス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 67ddf6a6712e0c98ea7b7866b3267d56308a5b5c
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="character-sequences"></a>文字シーケンス
**ANSI 3.8.2** ソース ファイルの文字シーケンスのマッピング  
  
 プリプロセッサ ステートメントは、ソース ファイル ステートメントと同じ文字セットを使用しますが、エスケープ シーケンスはサポートされていません。  
  
 したがって、インクルード ファイルのパスを指定するには、1 つの円記号 (バックスラッシュ) のみを使用します。  
  
```  
#include "path1\path2\myfile"  
```  
  
 ソース コード内では、次のように、2 つの円記号 (バックスラッシュ) が必要です。  
  
```  
fil = fopen( "path1\\path2\\myfile", "rt" );  
```  
  
## <a name="see-also"></a>関連項目  
 [プリプロセス ディレクティブ](../c-language/preprocessing-directives.md)
