---
title: "リソース コンパイラ エラー RC2104 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2104
dev_langs: C++
helpviewer_keywords: RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce7fa189e03ec907c4b42f381096f095d5df734a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2104"></a>リソース コンパイラ エラー RC2104
未定義のキーワードまたはキー名: キー  
  
 指定されたキーワードまたはキー名は定義されていません。  
  
 このエラーは、多くの場合、リソース定義または含まれているヘッダー ファイルの入力ミスによって発生します。 また、ヘッダー ファイルの欠落によって発生することもあります。  
  
 問題を解決するには、定義済みのキーワードまたはキー名が含まれているヘッダー ファイルを探し、それがリソース ファイルに含まれていることと、キーワードまたはキー名のスペルが正しいことを確認する必要があります。 プロジェクトがプリコンパイル済みヘッダーを使用して作成され、かつ、その後、それを削除した場合は、現在もリソース ファイルに必要なすべてのヘッダーが含まれていることを確認します。  
  
 定義のキーワードと、Visual Studio で、リソース ファイル内のキー名を確認するを開く、**リソース ビュー**ウィンドウ: メニュー バーで、次のように選択します**ビュー**、**リソース ビュー**: と.rc ファイルのショートカット メニューを開き、**リソース シンボル**に定義されたシンボルの一覧を表示します。 ヘッダーを変更する、.rc ファイルのショートカット メニューを開き**インクルード**です。  
  
 次のメッセージが発生した場合:  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 \MCL\MFC\Include\AfxRes.h を開いて次のインクルード ディレクティブを追加します。  
  
```  
#include <winresrc.h>  
```