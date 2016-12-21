---
title: "旧バージョンの Visual C++ からのプロジェクトのアップグレード | Microsoft Docs"
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
  - "32-bit code porting"
  - "upgrading Visual C++ applications, 32-bit code"
ms.assetid: 18cdacaa-4742-43db-9e4c-2d9e73d8cc84
caps.latest.revision: 36
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 旧バージョンの Visual C++ からのプロジェクトのアップグレード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどの場合、旧バージョンの Visual Studio で作成されたプロジェクトを開くことができます。 ただし、こうしたプロジェクトは、開くときにアップグレードされます。 アップグレードされたプロジェクトを保存すると、旧バージョンの Visual Studio では開くことができなくなります。  
  
> [!IMPORTANT]
>  既に変換されたプロジェクトを変換しようとすると、再変換によって既存のファイルが削除されるため、その旨を確認するメッセージが表示されます。  
  
 アップグレードされたプロジェクトおよびソリューションの多くが、変更なしで正常にビルドできます。 ただし、一部のプロジェクトについては、設定、ソース コード、またはその両方に対する変更が必要になる可能性があります。 まず、次のガイドラインを使用して、設定に関する問題に対処することをお勧めします。その後、プロジェクトをまだビルドできない場合は、コードの問題に対処します。  
  
1.  既存のプロジェクトおよびソリューション ファイルのコピーを作成します。 必要に応じてファイルのバージョンを比較できるように、現在のバージョンと旧バージョンの Visual Studio を並行してインストールします。  
  
2.  現在のバージョンの Visual Studio で、プロジェクトまたはソリューションのコピーを開いてアップグレードし、保存します。  
  
3.  変換されたプロジェクトごとに、ショートカット メニューを開き、**\[プロパティ\]** を選択します。**\[構成プロパティ\]** で **\[全般\]** を選択し、**\[プラットフォーム ツールセット\]** で現在のバージョンを選択します  \(たとえば、Visual Studio 2013 の場合は v120 を選択\)。  
  
4.  ソリューションをビルドします。 ビルドに失敗した場合は、設定を変更し、リビルドします。  
  
 ストアド プロシージャをデータ ソースで簡単に変更してデバッグできるように、そのソースは個別のデータベース プロジェクトに含まれています。 データ ソースが含まれる C\+\+ プロジェクトをアップグレードすると、個別のデータベース プロジェクトが自動的に作成されます。  
  
 対象となる Windows のバージョンを更新する方法については、「[WINVER および \_WIN32\_WINNT の変更](../porting/modifying-winver-and-win32-winnt.md)」を参照してください。  
  
## 参照  
 [ビルド システムの変更点](../build/build-system-changes.md)   
 [Visual C\+\+ 2015 での互換性に影響する変更点](../Topic/Visual%20C++%20change%20history%202003%20-%2020151.md)   
 [非標準動作](../Topic/Nonstandard%20Behavior.md)