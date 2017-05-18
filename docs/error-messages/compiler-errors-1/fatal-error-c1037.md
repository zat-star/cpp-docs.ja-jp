---
title: "致命的なエラー C1037 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1037
dev_langs:
- C++
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
caps.latest.revision: 7
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 892ce10f7d19266ce45d559ce35bc82946887c52
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1037"></a>致命的なエラー C1037
オブジェクト ファイル filename を開くことができません  
  
 指定されたオブジェクト ファイル[/Fo](../../build/reference/fo-object-file-name.md)開くことができません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ファイル名が無効です。  
  
2.  ファイルを開くためのメモリが不足しています。  
  
3.  別のプロセスでファイルを使用しています。  
  
4.  同じ名前の読み取り専用ファイルが存在します。  
  
 Visual C++ .NET (コンパイラ バージョン 1300) には、ファイル名 (またはファイル名へのディレクトリ パス) に MBCS 文字が含まれている場合に、ユーザー ロケールの正しい設定を要求するというバグがあります。 システム ロケールを設定するだけでは不十分です。MBCS 文字を処理するようにユーザー ロケールを設定する必要があります。
