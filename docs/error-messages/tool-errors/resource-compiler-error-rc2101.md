---
title: "リソース コンパイラ エラー RC2101 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 6
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 686c0b218ac4260fb796f60c1484c576a0c805b9
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101
プリプロセス済みの RC ファイルに無効なディレクティブ  
  
 リソース コンパイラのファイルに含まれる、 **#pragma**ディレクティブです。  
  
 使用して、 **#ifndef**インクルード ファイルを処理する際に、リソース コンパイラが定義される RC_INVOKED 定数とプリプロセッサ ディレクティブです。 場所、 **#pragma** RC_INVOKED 定数が定義されている場合に処理されていないコードのブロックの内部ディレクティブです。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードでは、この手法を示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma**プリプロセッサ ディレクティブ意味がない、です。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかで Microsoft によって提供される標準ヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルを含む、 **#pragma**ディレクティブです。 ヘッダー ファイルは、1 つまたは複数の他のヘッダー ファイルを含む、問題のあるファイルを含めることができますので**#pragma**ディレクティブをすぐにわかりにくいかもしれません。  
  
 **#Ifndef** RC_INVOKED 手法は、プロジェクト ベースのヘッダー ファイルでヘッダー ファイルを含む制御できます。
