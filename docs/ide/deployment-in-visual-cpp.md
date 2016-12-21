---
title: "Visual C++ での配置 | Microsoft Docs"
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
  - "アプリケーションの配置 [C++]"
  - "配置 (アプリケーションを) [C++]"
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ での配置
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] アプリケーションを別のコンピューターに配置する場合、アプリケーションと、アプリケーションが依存するすべてのライブラリ ファイルの両方をインストールする必要があります。  ライブラリが更新された場合、たとえば、セキュリティ上の脆弱性が修正された場合は、アプリケーションが配置されるすべての場所で更新プログラムを適用する必要があります。  
  
 Visual Studio では、集中配置、ローカル配置、静的リンクの 3 つの方法で、アプリケーションと共に [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリを配置できます。  集中配置されたライブラリは自動的に更新されます。  ローカル配置された、または静的にリンクされた [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリについては、アプリケーションの作成者が更新プログラムを提供する必要があります。  
  
## 集中配置  
 集中配置では、%windir%\\system32\\ ディレクトリに [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリ ファイルがインストールされます。  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリを集中配置するには、次のいずれかを使用します。  
  
-   *再頒布可能パッケージ ファイル*: [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 再頒布可能ライブラリのインストールに使用できるスタンドアロンのコマンド ライン実行可能ファイルです。  
  
-   *再頒布可能マージ モジュール \(.msm ファイル\)*: 特定のライブラリを配置する際に使用でき、アプリケーションの Windows インストーラー \(.msi\) ファイルに追加できます。  
  
 再頒布可能パッケージ ファイルにより、特定のシステム アーキテクチャの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリがインストールされます。  アプリケーション セットアップは、アプリケーションをインストールする前に必須コンポーネントとして実行されるようにプログラミングできます。  マージ モジュールにより、Windows インストーラーのアプリケーション セットアップ ファイルに、特定の [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリに対するセットアップ ロジックを含めることができます。  このマージ モジュールは、アプリケーションが必要とする数だけ使用できます。  
  
 再頒布可能パッケージを使用した [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリの集中配置では Microsoft による自動更新が可能であるため、アプリケーションには動的リンクと再頒布可能パッケージを使用することをお勧めします。  
  
## ローカル配置  
 ローカル配置では、ライブラリ ファイルが、実行可能ファイルと共にアプリケーション フォルダーにインストールされます。  ファイル名にバージョン番号が挿入されることで各バージョンのファイル名が一意になり、同じフォルダーにさまざまなバージョンのライブラリをインストールできます。  たとえば、C ランタイムの Version 12 は msvcr120.dll です。  
  
 ローカル配置された [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリは自動更新できないため、このライブラリのローカル配置については注意が必要です。  再頒布可能ライブラリのローカル配置を使用する場合は、ローカル配置されたライブラリを対象とした独自の自動更新方法を実装することをお勧めします。  
  
## 静的リンク  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリをアプリケーションに静的にリンクできます。つまり、アプリケーションにコンパイルできます。したがって、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリ ファイルは個別に配置する必要がありません。  ただし、静的にリンクされたライブラリはその場で更新できないため、このアプローチには注意が必要です。  静的なリンクを使用している場合、リンクされたライブラリを更新するには、アプリケーションを再コンパイルし、再配置する必要があります。  
  
## トラブルシューティング  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリの読み込み順序はシステムに依存します。  ローダーの問題を診断するには、depends.exe または where.exe を使用します。  詳細については、「[Dynamic\-Link Library Search Order \(ダイナミック リンク ライブラリの検索順序\)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)」を参照してください。  
  
## 参照  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)