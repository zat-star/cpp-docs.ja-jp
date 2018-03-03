---
title: "リソース コンパイラ エラー RC2101 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d08e9ddb7b8cda127b1d05bfef52b52833534cb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2101"></a>リソース コンパイラ エラー RC2101
プリプロセス済みの RC ファイルに無効なディレクティブ  
  
 リソース コンパイラのファイルが含まれています、 **#pragma**ディレクティブです。  
  
 使用して、 **#ifndef**プリプロセッサ ディレクティブの中でインクルード ファイルを処理する際に、リソース コンパイラが定義される RC_INVOKED 定数。 場所、 **#pragma** RC_INVOKED 定数が定義されている場合は処理されていないコードのブロックの内側ディレクティブです。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードは、この手法を示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma**プリプロセッサ ディレクティブ意味がない、します。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかの Microsoft によって提供される標準ヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブです。 ヘッダー ファイルが 1 つまたは複数の他のヘッダー ファイル、問題のあるを格納しているファイルを含めることができますので**#pragma**ディレクティブをすぐに判断できない可能性があります。  
  
 **#Ifndef**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルを含む RC_INVOKED 方法を制御できます。