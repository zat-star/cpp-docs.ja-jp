---
title: "致命的なエラー C1010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1010
dev_langs:
- C++
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b2123118be2a8a382f6b718499c5af16f88d111
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1010"></a>致命的なエラー C1010
プリコンパイル ヘッダーを検索中に不明な EOF が見つかりました。 追加忘れました ' # 名 include' をソースですか?  
  
 指定されたインクルード ファイル[/Yu](../../build/reference/yu-use-precompiled-header-file.md)ソース ファイルには表示されません。  既定ではほとんどの Visual C プロジェクトの種類では、このオプションが有効になっているし、"stdafx.h"が既定値は、このオプションで指定されたファイルを含めます。  
  
 Visual Studio 環境でこのエラーを解決するのには、次のメソッドのいずれかを使用します。  
  
-   プロジェクトでプリコンパイル済みヘッダーを使用しない場合は、設定、**プリコンパイル済みヘッダーの作成/使用**するソース ファイルのプロパティ**プリコンパイル済みヘッダーを使用して**です。 このコンパイラ オプションを設定するには、次の手順を実行します。  
  
    1.  プロジェクトの [ソリューション エクスプ ローラー] ウィンドウでプロジェクト名を右クリックし、をクリックして**プロパティ**です。  
  
    2.  左側のウィンドウでをクリックして、 **C/C++**フォルダーです。  
  
    3.  クリックして、**プリコンパイル済みヘッダー**ノード。  
  
    4.  右側のウィンドウでをクリックして**プリコンパイル済みヘッダーの作成/使用**、クリックして**プリコンパイル済みヘッダーを使用しない**です。  
  
-   誤って削除、名前変更、またはヘッダー ファイルを削除するかどうかを確認 (既定では、stdafx.h) 現在のプロジェクトからです。 このファイルも含める必要がありますを使用して、ソース ファイル内の他のすべてのコードの前に**#include"stdafx.h"**です。 (このヘッダー ファイルとして指定**ファイルを作成/使用 PCH**プロジェクトのプロパティ)