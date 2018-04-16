---
title: "リソース コンパイラ エラー RW2001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a14cd36ab87297cf5bc0aa547bdea5ef23260e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2001"></a>リソース コンパイラ エラー RW2001
プリプロセス済みの RC ファイルに無効なディレクティブ  
  
 RC ファイルが含まれています、 **#pragma**ディレクティブです。  
  
 使用して、 **#ifndef**プリプロセッサ ディレクティブの中で、 **RC_INVOKED**リソース コンパイラのインクルード ファイルを処理する際に定義する定数。 場所、 **#pragma**されていないコードのブロックの内側ディレクティブ処理時に、 **RC_INVOKED**定数が定義されています。 C と C++ コンパイラでのみ、リソース コンパイラではなく、ブロック内のコードが処理されます。 次のサンプル コードは、この手法を示します。  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma**プリプロセッサ ディレクティブ意味がない、します。RC ファイルです。 **#Include**プリプロセッサ ディレクティブで頻繁に使用します。ヘッダー ファイル (プロジェクト ベースのカスタム ヘッダー ファイルまたはその製品のいずれかの Microsoft によって提供される標準ヘッダー ファイル) を含める RC ファイルです。 これらのいくつかのインクルード ファイルが含まれて、 **#pragma**ディレクティブです。 ヘッダー ファイルが 1 つまたは複数の他のヘッダー ファイル、問題のあるを格納しているファイルを含めることができますので**#pragma**ディレクティブをすぐに判断できない可能性があります。  
  
 **#Ifndef RC_INVOKED**プロジェクト ベースのヘッダー ファイル内のヘッダー ファイルを含む方法を制御できます。