---
title: "配置の概念 | Microsoft Docs"
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
  - "アプリケーションの配置 [C++], アプリケーションの配置の概要"
  - "依存関係 [C++], アプリケーションの配置"
  - "配置 (アプリケーションを) [C++], 配置の概要 (アプリケーションの)"
  - "ライブラリ [C++], アプリケーションの配置の問題"
  - "Windows インストーラー [C++]"
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 配置の概念
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このセクションでは、C\+\+ アプリケーションを配置するうえでの主な考慮事項について説明します。  
  
## C\+\+ での Windows インストーラーの配置  
 一般に、Visual C\+\+ プロジェクトの配置には、従来の Windows インストーラーによるセットアップを使用します。  Windows インストーラーを配置できるようにするには、アプリケーションを setup.exe ファイルにパッケージ化し、そのファイルをインストーラー パッケージ \(.msi\) と共に配布します。  その後、ユーザーは、setup.exe を実行してアプリケーションをインストールします。  
  
 アプリケーションをパッケージ化するには、セットアップ プロジェクトをソリューションに追加します。これにより、ユーザーに配布するセットアップ ファイルとインストーラー パッケージ ファイルがビルド時に作成されます。  詳細については、「[配置方法の選択](../ide/choosing-a-deployment-method.md)」を参照してください。  
  
## ライブラリの依存関係  
 Visual C\+\+ ライブラリに用意された機能を使用して C\/C\+\+ アプリケーションをビルドすると、C\/C\+\+ アプリケーションは、実行時にそれらのライブラリの存在に依存するようになります。  アプリケーションを実行するには、静的または動的に、必要な Visual C\+\+ ライブラリにリンクする必要があります。  アプリケーションが動的に Visual C\+\+ ライブラリにリンクしている場合、アプリケーションの実行時には、そのライブラリが存在し、読み込むことができる必要があります。  それに対してアプリケーションが静的に Visual C\+\+ ライブラリにリンクしている場合は、対応する DLL がユーザーのコンピューター上に存在する必要はありません。  ただし、静的なリンクにはいくつかの短所があります。たとえば、アプリケーション ファイルのサイズが大きくなったり、場合によっては保守が困難になったりします。  詳細については、「[DLL の利点](../build/advantages-of-using-dlls.md)」を参照してください。  
  
## パッケージ化と再配布  
 Visual C\+\+ ライブラリは DLL としてパッケージ化され、C\/C\+\+ アプリケーションに必要なすべてのライブラリは、Visual Studio によって開発者のコンピューターにインストールされます。  ただし、アプリケーションをユーザーに配置するときに、そのアプリケーションを実行するためにユーザーに対して Visual Studio のインストールを求めることは、ほとんどの場合は不可能です。  アプリケーションを正しく実行するために必要な Visual C\+\+ の部分のみを再配布できることが重要です。  
  
 パッケージ化と再配布の詳細については、次のトピックを参照してください。  
  
-   [再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [配置方法の選択](../ide/choosing-a-deployment-method.md).  
  
 配置のサンプルとトラブルシューティングの詳細については、次のトピックを参照してください。  
  
-   [配置例](../ide/deployment-examples.md).  
  
-   [トラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## 参照  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)   
 [Visual C\+\+ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/ja-jp/121be21b-b916-43e2-8f10-8b080516d2a0)