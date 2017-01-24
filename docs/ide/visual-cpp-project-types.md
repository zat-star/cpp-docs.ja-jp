---
title: "Visual C++ プロジェクトの種類 | Microsoft Docs"
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
  - "プログラム [C++]、プロジェクト"
  - "プロジェクト テンプレート [Visual Studio]、C++"
  - "TODO コメント [C++]"
  - "プロジェクト [C++]、種類"
  - "テンプレート [C++]、プロジェクト"
  - "アプリケーション [C++]、プロジェクト"
  - "Visual C++ プロジェクト、種類"
ms.assetid: 7337987e-1e7b-4120-9a4b-94f0401f15e7
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ プロジェクトの種類
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロジェクト テンプレートを使用して、基本的なプログラムの構造、メニュー、ツール バー、アイコン、参照、および作成するプロジェクトの種類に適した `#include` ステートメントを作成できます。 Visual Studio には、数種類の Visual C\+\+ プロジェクト テンプレートが含まれ、これらのテンプレートの多くにはウィザードが用意されているため、プロジェクトを作成しながらカスタマイズを行うことができます。 プロジェクトを作成したらすぐにプロジェクトをビルドし、アプリケーションを実行できます。アプリケーションを開発しながら、断続的にビルドすることをお勧めします。  
  
 プロジェクトの作成にテンプレートを使用する必要はありませんが、多くの場合、テンプレートを使用した方が効率的です。用意されたプロジェクト ファイルおよび構造を修正する方が、初めから作成するよりも簡単なためです。  
  
> [!NOTE]
>  C\+\+ プロジェクト テンプレートを使用して C 言語プロジェクトを作成できます。 生成されたプロジェクトで、.cpp ファイル名拡張子を持つファイルを検索して .c に変更します。 次に、プロジェクト \(ソリューションではない\) の **\[プロジェクトのプロパティ\]** ページで、**\[構成プロパティ\]**、**\[C\/C\+\+\]** の順に展開し、**\[詳細\]** を選択します。**\[コンパイル言語の選択\]** 設定を **\[C コードとしてコンパイル \(\/TC\)\]** に変更します。  
  
## プロジェクト テンプレート  
 Visual Studio には、次の Visual C\+\+ プロジェクト テンプレートが用意されています。  
  
### ストア アプリ  
  
||  
|-|  
|[ストア アプリ用の C\#、VB、C\+\+ のプロジェクト テンプレート](http://go.microsoft.com/fwlink/p/?LinkID=262279)|  
  
### ATL  
  
|プロジェクト テンプレート|プロジェクトを作成する方法|  
|-------------------|-------------------|  
|ATL プロジェクト|[ATL プロジェクトの作成](../atl/reference/creating-an-atl-project.md)|  
  
### CLR  
  
|プロジェクト テンプレート|  
|-------------------|  
|[\(NOTINBUILD\)Class ライブラリ テンプレート \(C\+\+\)](http://msdn.microsoft.com/ja-jp/0d779bfa-5c5a-4b10-a9d5-a6791764a78f)|  
|[方法 : CLR コンソール アプリケーションを作成する](../Topic/How%20to:%20Create%20CLR%20Console%20Applications%20\(C++-CLI\).md)|  
|[NOTINBUILD CLR 空のプロジェクト テンプレート \(C\+\+\)](http://msdn.microsoft.com/ja-jp/f57c5572-5581-440f-b684-eec646764f08)|  
  
### 全般  
  
|プロジェクト テンプレート|プロジェクトを作成する方法|  
|-------------------|-------------------|  
|空のプロジェクト|[ソリューションとプロジェクトの作成](../Topic/Creating%20Solutions%20and%20Projects.md)|  
|カスタム ウィザード|[カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)|  
|メイクファイル プロジェクト|[メイクファイル プロジェクトの作成](../ide/creating-a-makefile-project.md)|  
  
### MFC  
  
|プロジェクト テンプレート|プロジェクトを作成する方法|  
|-------------------|-------------------|  
|MFC ActiveX コントロール|[MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)|  
|MFC アプリケーション|[MFC アプリケーションの作成](../mfc/reference/creating-an-mfc-application.md)|  
|MFC DLL|[MFC DLL プロジェクトの作成](../mfc/reference/creating-an-mfc-dll-project.md)|  
  
### テスト  
  
|プロジェクト テンプレート|プロジェクトを作成する方法|  
|-------------------|-------------------|  
|マネージ テスト プロジェクト|[単体テスト プロジェクトを作成する](../Topic/Create%20a%20unit%20test%20project.md)|  
|ネイティブ単体テスト プロジェクト|[テスト エクスプローラーを使用したネイティブ コードの単体テスト](http://msdn.microsoft.com/ja-jp/8a09d6d8-3613-49d8-9ffe-11375ac4736c)|  
  
### Win32  
  
|プロジェクト テンプレート|プロジェクトを作成する方法|  
|-------------------|-------------------|  
|Win32 コンソール プロジェクト|[コンソール アプリケーションの作成](../windows/creating-a-console-application.md)|  
|Win32 プロジェクト|[方法: Windows デスクトップ アプリケーションの作成](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)|  
  
## TODO コメント  
 プロジェクト テンプレートによって生成されたファイルの多くには TODO コメントが含まれています。このコメントは、独自のソース コードを作成できる場所を特定するのに役立ちます。 コードの追加方法について詳しくは、「[コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)」および「[Working with Resource Files](../mfc/working-with-resource-files.md)」をご覧ください。  
  
## 参照  
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [アプリケーションを作成するためのプロジェクトの使用](http://msdn.microsoft.com/ja-jp/3339fa90-bac2-4b95-8361-662a2e0e7dfe)   
 [CLR プロジェクト](../ide/files-created-for-clr-projects.md)