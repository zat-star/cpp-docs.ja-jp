---
title: "[詳細] ([MIDL] プロパティ ページ) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCMidlTool.ErrorCheckBounds"
  - "VC.Project.VCMidlTool.ErrorCheckStubData"
  - "VC.Project.VCMidlTool.ErrorCheckAllocations"
  - "VC.Project.VCMidlTool.CPreprocessOptions"
  - "VC.Project.VCMidlTool.UndefinePreprocessorDefinitions"
  - "VC.Project.VCMidlTool.EnableErrorChecks"
  - "VC.Project.VCMidlTool.RedirectOutputAndErrors"
  - "VC.Project.VCMidlTool.ErrorCheckEnumRange"
  - "VC.Project.VCMidlTool.StructMemberAlignment"
  - "VC.Project.VCMidlTool.ErrorCheckRefPointers"
  - "VC.Project.VCMidlTool.ValidateParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MIDL、プロパティ ページ"
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# [詳細] ([MIDL] プロパティ ページ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\[MIDL\] フォルダーの \[詳細\] プロパティ ページでは、以下の MIDL コンパイラ オプションを指定します。  
  
-   エラーのチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   メモリの割り当てをチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   範囲のチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   enum の範囲のチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   参照ポインターのチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   スタブ データのチェック \([\/error](http://msdn.microsoft.com/library/windows/desktop/aa367324)\)  
  
-   パラメーターの有効化 \([\/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)\) \*  
  
-   構造体メンバーのアラインメント \([\/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388)\)  
  
-   出力先の変更 \([\/o](http://msdn.microsoft.com/library/windows/desktop/aa367351)\)  
  
-   C プリプロセス オプション \([\/cpp\_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318)\)  
  
-   プリプロセッサ定義の解除 \([\/U](http://msdn.microsoft.com/library/windows/desktop/aa367373)\)  
  
 \* \/robust は、Windows 2000 以降のコンピューター用にビルドするときだけ使用します。  ATL プロジェクトのビルド時に \/robust を使用する場合は、dlldatax.c ファイルの以下の行を変更してください。  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 \[MIDL\] フォルダーの \[詳細\] プロパティ ページを表示する方法については、「[方法 : &#91;プロパティ ページ&#93; でプロジェクトのプロパティを指定する](../Topic/How%20to:%20Specify%20Project%20Properties%20with%20Property%20Pages.md)」を参照してください。  
  
 C\+\+ プロジェクト用の MIDL オプションにプログラムでアクセスする方法については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>」を参照してください。  
  
## 参照  
 [\[MIDL\] プロパティ ページ](../Topic/MIDL%20Property%20Pages.md)