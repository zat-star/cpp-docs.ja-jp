---
title: "Windows Vista コモン コントロールの作成要件 | Microsoft Docs"
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
  - "コモン コントロール (MFC)"
  - "コモン コントロール (MFC), ビルドの要件"
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Windows Vista コモン コントロールの作成要件
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation Class \(MFC\) ライブラリは Windows コモン コントロール バージョン 6.1 をサポートします。  コモン コントロールは [!INCLUDE[windowsver](../Token/windowsver_md.md)] に含まれ、[!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]に含まれます。  ライブラリは、既存のクラスを拡張し、[!INCLUDE[windowsver](../Token/windowsver_md.md)]コモン コントロールをサポートするメソッドと新しいクラスです。新しいメソッド。  アプリケーションをビルドする場合は、次のセクションで説明するコンパイルおよび移行に関する要件に従う必要があります。  
  
## コンパイル要件  
  
### サポートされているバージョン  
 他のメソッドでは、旧バージョンのオペレーティング システムがサポートされますが、新しいクラスとメソッドは [!INCLUDE[windowsver](../Token/windowsver_md.md)] だけを後でサポートします。  各メソッドの `Requirements` セクションの説明は必要最小限のオペレーティング システムが [!INCLUDE[windowsver](../Token/windowsver_md.md)]になったかどうかを指定します。  
  
 コンピューターが [!INCLUDE[windowsver](../Token/windowsver_md.md)]を実行しない場合でも、コンピューター上でバージョン 6.1 MFC ヘッダー ファイルがある場合 [!INCLUDE[windowsver](../Token/windowsver_md.md)] で実行する MFC アプリケーションをビルドできます。  ただし、[!INCLUDE[windowsver](../Token/windowsver_md.md)] 用に設計されているコモン コントロールは、そのシステムでのみ機能し、以前のオペレーティング システムでは無視されます。  
  
### サポートされている文字セット  
 新しい Windows コモン コントロールは、Unicode 文字セットだけで、ANSI 文字セットをサポートします。  アプリケーションをコマンド ラインでビルドする場合は、以下の両方を定義して使用します \(\/D\)、基になる文字セットとして Unicode を指定するコンパイラ オプション:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Visual Studio 統合開発環境 \(IDE\) でアプリケーションをビルドする場合は、プロジェクトのプロパティ **\[全般\]** ノードで **\[文字セット\]** のプロパティの **\[Unicode 文字セット\]** オプションを指定します。  
  
 複数の MFC メソッドの ANSI バージョンは Windows コモン コントロール バージョン、6.1 から使用されなくなった開始です。  詳細については、「[サポートされなくなった ANSI API](../mfc/deprecated-ansi-apis.md)」を参照してください。  
  
## 移行の要件  
 Windows コモン コントロール Version 6.1 を使用する新しい MFC アプリケーションを作成するために Visual Studio IDE を使用して、IDE で自動的に適切なマニフェストを宣言します。  ただし、Visual Studio の旧バージョンで作成した既存の MFC アプリケーションを移行し、新しいコモン コントロールを使用する場合は、IDE で自動的にアプリケーションをアップグレードするマニフェスト情報は提供しません。  代わりに、stdafx.h ファイルに手動で次のソース・コードを挿入する必要があります:  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## 参照  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [階層図](../mfc/hierarchy-chart.md)   
 [サポートされなくなった ANSI API](../mfc/deprecated-ansi-apis.md)