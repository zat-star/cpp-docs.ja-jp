---
title: "致命的なエラー C1854 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1854
dev_langs: C++
helpviewer_keywords: C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e0a26e902b1a40203bb4323bce8e28e687e9647
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1854"></a>致命的なエラー C1854
  
> オブジェクト ファイルでプリコンパイル済みヘッダーの作成中に情報を上書きすることはできません: '*filename*'  
  
指定した、 [/Yu (プリコンパイル済みヘッダー ファイルの使用)](../../build/reference/yu-use-precompiled-header-file.md)オプションを指定したら、 [/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)同じファイル オプションを指定します。  
  
この問題を解決するを使用してコンパイルするプロジェクトで一般に、1 つのファイルを設定、 **/Yc**オプション、および設定を使用してコンパイルする他のすべてのファイル、 **/Yu**オプション。 使用に関する詳細について、 **/Yc**オプション、および Visual Studio IDE で設定する方法[/Yc (プリコンパイル済みヘッダー ファイルの作成)](../../build/reference/yc-create-precompiled-header-file.md)です。 プリコンパイル済みヘッダーの使用の詳細については、次を参照してください。[プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)です。  
