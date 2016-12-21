---
title: "Visual C++ アプリケーションの ClickOnce 配置 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "配置 (アプリケーションを) [C++]、ClickOnce"
  - "アプリケーションの配置 [C++]、ClickOnce"
  - "ClickOnce の配置 [C++]、C++ アプリケーション"
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ アプリケーションの ClickOnce 配置
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] には、2 とおりの Windows アプリケーションの配置方法があります。ClickOnce を使用する方法と [Windows インストーラー](http://msdn.microsoft.com/library/cc185688)を使用する方法です。  
  
## C\+\+ の ClickOnce 配置  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 開発環境では [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] による [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] プロジェクトの配置は直接はサポートされませんが、それを使用するためのツールを利用できます。  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] は [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] および [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] 開発環境で [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] をサポートします。  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] プロジェクトが [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] プロジェクトの依存関係である場合は、[!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] 開発環境から [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] 配置を使用して、アプリケーションを \(その依存関係を含めて\) 発行できます。  
  
 [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] を使用して [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] アプリケーションを配置するには、[Mage.exe \(マニフェストの生成および編集ツール\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) またはそのグラフィカル ユーザー インターフェイス バージョン \(詳細については「[MageUI.exe \(マニフェスト生成および編集ツールのグラフィカル クライアント\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)」を参照\) を使用して、最初に [ClickOnce アプリケーション マニフェスト](../Topic/ClickOnce%20Application%20Manifest.md)および [ClickOnce 配置マニフェスト](../Topic/ClickOnce%20Deployment%20Manifest.md)を作成する必要があります。  
  
 最初に、Mage.exe を使用してアプリケーション マニフェストをビルドします。作成されるファイルには拡張子 .manifest が付きます。  次に、Mage.exe を使用して配置マニフェストをビルドします。作成されるファイルには拡張子 .application が付きます。  次にマニフェストに署名します。  
  
 アプリケーション マニフェストでは、対象となるプロセッサ \(**x86**、**x64**、または **ARM**\) を指定する必要があります。  これらのオプションの詳細については、「[64 ビット アプリケーションの配置のための必要条件](../Topic/Deploying%20Prerequisites%20for%2064-bit%20Applications.md)」を参照してください。  
  
 また、アプリケーション マニフェストと配置マニフェストの名前は C\+\+ アプリケーションの名前と異なっている必要があります。  これによって、Mage.exe で作成されるアプリケーション マニフェストと C\+\+ アプリケーションの一部である外部マニフェストの間の競合を回避できます。  
  
 配置では、アプリケーションが依存する [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリをインストールする必要があります。  特定のアプリケーションの依存関係を確認するには、depends.exe または DUMPBIN ユーティリティを \/DEPENDENTS オプションと共に使用します。  依存関係の詳細については、「[Visual C\+\+ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)」を参照してください。  VCRedist.exe の実行が必要な場合もあります。このユーティリティはターゲット コンピューターに [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリをインストールします。  
  
 さらに、アプリケーションが必須コンポーネントを配置するために、ブートストラップ \(必須コンポーネント インストーラー\) をビルドする必要があることもあります。ブートストラップの詳細については、「[ブートストラップ パッケージの作成](../Topic/Creating%20Bootstrapper%20Packages.md)」を参照してください。  
  
 テクノロジの詳細については、「[ClickOnce のセキュリティと配置](../Topic/ClickOnce%20Security%20and%20Deployment.md)」を参照してください。  [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] 配置の詳細な例については、「[チュートリアル : ClickOnce アプリケーションを手動で配置する](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)」を参照してください。  
  
## 参照  
 [Mage.exe \(マニフェストの生成および編集ツール\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(マニフェスト生成および編集ツールのグラフィカル クライアント\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe \(証明書作成ツール\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)   
 [アプリケーション、サービス、およびコンポーネントの配置](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/ja-jp/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce のセキュリティと配置](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [ブートストラップ パッケージの作成](../Topic/Creating%20Bootstrapper%20Packages.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)