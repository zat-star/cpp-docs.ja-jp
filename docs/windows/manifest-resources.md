---
title: "Manifest Resources | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "manifest resources"
  - "resources [Visual Studio], manifest"
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Manifest Resources
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マニフェスト リソースは、アプリケーションで使用される依存関係を記述する XML ファイルです。 たとえば Visual Studio では、MFC ウィザードで生成されたマニフェスト ファイルで、アプリケーションがバージョン 5.0 と 6.0 のどちらの Windows コモン コントロール DLL を使用するかを定義します。  
  
```  
<description>Your app description here</description> <dependency> <dependentAssembly> <assemblyIdentity type="win32" name="Microsoft.Windows.Common-Controls" version="6.0.0.0" processorArchitecture="X86" publicKeyToken="6595b64144ccf1df" language="*" /> </dependentAssembly> </dependency>   
```  
  
 Windows XP または Windows Vista アプリケーションのマニフェスト リソースは、アプリケーションで最新バージョンの Windows コモン コントロール \(上の例で示すようにバージョン 6.0\) を使用することを指定するだけではなく、[Syslink コントロール](http://msdn.microsoft.com/library/windows/desktop/bb760706)をサポートします。  
  
 マニフェスト リソースに含まれるバージョン情報とタイプ情報を参照するには、XML ビューアーや Visual Studio の[テキスト エディター](http://msdn.microsoft.com/ja-jp/508e1f18-99d5-48ad-b5ad-d011b21c6ab1)でファイルを開きます。 詳細については、[Visual Studio テキスト エディターでマニフェスト リソースを開く方法](../Topic/How%20to:%20Open%20a%20Manifest%20Resource.md)に関するページを参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『*.NET Framework 開発者ガイド*』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md) を参照してください。  
  
## 制限事項  
 使用できるマニフェスト リソースは 1 つのモジュールにつき 1 つだけです。  
  
## 必要条件  
 Win32  
  
## 参照  
 [コントロール](../mfc/controls-mfc.md)   
 [Working with Resource Files](../mfc/working-with-resource-files.md)