---
title: "致命的なエラー C1010 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1010"
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 致命的なエラー C1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリコンパイル ヘッダーを検索中に不明な EOF が見つかりました。'\#include '名前'' をソースに追加することをお勧めします。  
  
 [\/Yu](../../build/reference/yu-use-precompiled-header-file.md) で指定されたインクルード ファイルがソース ファイルにリストされていません。このオプションは、ほとんどの種類の Visual C\+\+ プロジェクトで既定で有効になっています。また、このオプションで指定される既定のインクルード ファイルは "stdafx.h" です。  
  
 Visual Studio 環境では、このエラーを解決するには、以下のいずれかの方法を使用します。  
  
-   プロジェクトでプリコンパイル済みヘッダーを使用しない場合は、ソース ファイルの \[プリコンパイル済みヘッダーの作成\/使用\] プロパティを **\[プリコンパイル済みヘッダーを使用しない\]** に設定します。  このコンパイラ オプションを設定するには、次の手順を実行します。  
  
    1.  プロジェクトのソリューション エクスプローラー ペインで、プロジェクト名を右クリックし、**\[プロパティ\]** をクリックします。  
  
    2.  左ペインの \[**C\/C\+\+**\] フォルダーをクリックします。  
  
    3.  \[プリコンパイル済みヘッダー\] ノードをクリックします。  
  
    4.  右ペインの \[プリコンパイル済みヘッダーの作成\/使用\] をクリックし、**\[プリコンパイル済みヘッダーを使用しない\]** をクリックします。  
  
-   誤ってヘッダー ファイル \(既定では stdafx.h\) を削除したり、名前を変更したり、現在のプロジェクトから除去したりしていないことを確認します。  また、このファイルは、ソース ファイル内で他のコードより前に、**\#include "stdafx.h"** を使用してインクルードされている必要があります \(このヘッダー ファイルは、\[ファイルを使用して PCH を作成\/使用\] プロジェクト プロパティとして指定されます\)。