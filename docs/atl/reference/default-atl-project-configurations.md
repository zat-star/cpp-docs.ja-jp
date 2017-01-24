---
title: "ATL プロジェクトの既定の構成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, 既定の構成"
ms.assetid: 7e272722-41af-4330-b965-a6d74ec16880
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL プロジェクトの既定の構成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、Visual C\+\+ .NET の ATL プロジェクトの既定の構成と、Visual C\+\+ 6.0 の既定のプロジェクト構成を比較します。  
  
## Visual C\+\+ .NET の既定の構成  
 Visual C\+\+ .NET では、ATL プロジェクト ウィザードによって 2 つのプロジェクト構成が既定で作成されます。  
  
### Visual C\+\+ .NET の構成  
  
|構成|文字セット|ATL の使用|  
|--------|-----------|-------------|  
|リリース|MBCS|\[DLL\]|  
|デバッグ|MBCS|\[DLL\]|  
  
 \[文字セット\]、**\[ATL の使用\]** は、\[プロジェクトの設定\] ダイアログ ボックスの \[全般\] タブですべて変更できます。  また、構成マネージャーを使用して独自の構成も追加できます。  詳細については、「[ビルド構成](../Topic/Understanding%20Build%20Configurations.md)」を参照してください。  
  
## Version 6.0 の既定の構成  
 Visual C\+\+ Version 6.0 では、ATL COM AppWizard \(現在は ATL プロジェクト ウィザード\) によって 6 つのプロジェクト構成が既定で作成されます。  これらの構成はリリース、デバッグ、Unicode、および CRT 設定と ATL 設定の使用が変化したものです。  これらの構成はすべて、構成マネージャーを使用して、必要に応じて Visual C\+\+ .NET に複製できます。  
  
### Version 6.0 の構成  
  
|構成|文字セット|ATL の使用|  
|--------|-----------|-------------|  
|デバッグ|MBCS|静的|  
|デバッグ Unicode バージョン|UNICODE|静的|  
|リリース最小依存バージョン|MBCS|静的|  
|リリース最小依存 Unicode バージョン|UNICODE|静的|  
|リリース最小サイズ バージョン|MBCS|\[DLL\]|  
|リリース最小サイズ Unicode バージョン|UNICODE|\[DLL\]|  
  
## 参照  
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)   
 [Configuration Manager Dialog Box](http://msdn.microsoft.com/ja-jp/fa182dca-282e-4ae5-bf37-e155344ca18b)   
 [Visual Studio でのアプリケーションのビルド](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)