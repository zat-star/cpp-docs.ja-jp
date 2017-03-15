---
title: "ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ファイルの種類 [C++], ATL ソースとヘッダー"
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio で ATL プロジェクトを作成すると、以下のファイルが作成されます。作成されるファイルは、プロジェクトに対して指定したオプションによって異なります。  
  
 これらのファイルはすべて、*Projname* ディレクトリ、およびソリューション エクスプローラーの \[ヘッダー ファイル\] \(.h ファイルの場合\) フォルダーか \[ソース ファイル\] \(.cpp ファイルの場合\) フォルダーにあります。  
  
|ファイル名|Description|  
|-----------|-----------------|  
|*Projname*.h|主要なインクルード ファイル。ATLSample.idl で定義された項目の C\+\+ インターフェイス定義および GUID 宣言が記述されています。  コンパイル時に MIDL によって再度生成されます。|  
|*Projname*.cpp|プログラムの主要なソース ファイル。  このファイルには、インプロセス サーバー用の DLL エクスポートの実装と、ローカル サーバー用の `WinMain` の実装が含まれます。  また、サービスに対しては、すべてのサービス管理関数を実装します。|  
|Resource.h|リソース ファイル用のヘッダー ファイルです。|  
|StdAfx.cpp|StdAfx.h ファイルと Atlimpl.cpp ファイルが含まれます。|  
|StdAfx.h|ATL ヘッダー ファイルが含まれます。|  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)