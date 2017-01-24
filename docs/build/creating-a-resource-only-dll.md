---
title: "リソースのみの DLL の作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL [C++], 作成"
  - "リソース専用 DLL [C++], 作成"
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リソースのみの DLL の作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースのみの DLL とは、リソース以外のものを一切含まず、アイコン、ビットマップ、文字列、ダイアログ ボックスだけを含む DLL です。  リソースのみの DLL は、複数のプログラム間でリソース群を共有するのに適しています。  また、混合言語を使用できるようにローカライズされたリソースをアプリケーションに提供する方法としても最適です。詳細については、「[MFC アプリケーションのローカライズされたリソース : サテライト DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)」を参照してください。  
  
 リソースのみの DLL を作成するには、Win32 DLL \(非 MFC\) プロジェクトを新規作成し、ここにリソースを追加します。  
  
-   **\[新しいプロジェクト\]** ダイアログ ボックスの \[Win32 プロジェクト\] を選択し、Win32 プロジェクト ウィザードの DLL プロジェクト タイプを指定します。  
  
-   DLL 用のリソース \(文字列やメニューなど\) を含むリソース スクリプトを新規作成し、.rc ファイルに保存します。  
  
-   \[プロジェクト\] メニューの **\[既存項目の追加\]** をクリックし、新しい .rc ファイルをプロジェクトに追加します。  
  
-   [\/NOENTRY](../build/reference/noentry-no-entry-point.md) リンカー オプションを指定します。\/NOENTRY を指定すると、\_main への参照が DLL にリンクされません。リソースのみの DLL を作成する場合は、このオプションを指定する必要があります。  
  
-   DLL をビルドします。  
  
 リソースのみの DLL を使用するアプリケーションでは、**LoadLibrary** を呼び出して [DLL に明示的にリンクする](../build/loadlibrary-and-afxloadlibrary.md)必要があります。  リソースにアクセスするには、ジェネリック関数 **FindResource** と **LoadResource** を呼び出します。これらの関数は、リソースの種類に関係なく動作し、以下のリソース固有関数の中の 1 つを呼び出します。  
  
-   `FormatMessage`  
  
-   **LoadAccelerators**  
  
-   `LoadBitmap`  
  
-   `LoadCursor`  
  
-   `LoadIcon`  
  
-   `LoadMenu`  
  
-   `LoadString`  
  
 アプリケーションはリソースを使い終わった時点で、**FreeLibrary** を呼び出す必要があります。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [DELETE\_PENDING\_Editing Resources](http://msdn.microsoft.com/ja-jp/c29d31c7-2d94-40ca-8aa0-c7262883529c)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)