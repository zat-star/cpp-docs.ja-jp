---
title: "致命的なエラー C1047 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5b23d0dd38806e613f0066002cc73b143956225c
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1047"></a>致命的なエラー C1047
オブジェクトまたはライブラリ ファイル 'file' は、他のオブジェクトよりも古いコンパイラで作成されました。古いオブジェクトおよびライブラリをリビルドしてください  
  
 C1047 は、 **/LTCG** を指定してビルドされたオブジェクト ファイルまたはライブラリがリンクされるときに、それらのオブジェクト ファイルまたはライブラリが、異なるバージョンの Visual C++ ツールセットでビルドされている場合に発生します。  
  
 これは、新しいバージョンのコンパイラの使用を開始するときに、既存のオブジェクト ファイルまたはライブラリをクリーンにリビルドしない場合に発生することがあります。  
  
 C1047 を解決するには、オブジェクト ファイルまたはライブラリをすべてリビルドします。
