---
title: "以前のランタイム バージョンで C++ と clr アプリケーションの実行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f64c0dc31be260332d4d79e8fa38d63bbf6357c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>以前のランタイム バージョンでの C++ /clr アプリケーションの実行
未指定のそれ以外の場合、コンパイラが、アプリケーションをビルドに使用するバージョンの共通言語ランタイム (CLR) で実行する、C++ の .NET Framework のアプリケーションが作成されています。 ただし、1 つのバージョンの必要な機能を提供するその他のバージョンで実行するランタイムの構築された .exe アプリケーションです。  
  
 これを実現するには、ランタイム バージョン情報を含む app.config ファイルを提供、`supportedRuntime`タグ。  
  
 実行時に、app.config ファイルが、フォームの名前をいる必要があります*.ext という*.config を場所*.ext という*アプリケーションを開始した実行可能ファイルの名前を指定し、これと同じディレクトリに存在する必要があります実行可能ファイルです。 たとえば、アプリケーションが TestApp.exe をという名前の場合、app.config ファイルの名前は TestApp.exe.config します。  
  
 1 つ以上のランタイム バージョンを指定して、1 つ以上インストールされているランタイム バージョンをあるコンピューターでアプリケーションを実行する場合、アプリケーションがインストールされている構成ファイルで指定されている最初のバージョンを使用します。  
  
 詳細については、次を参照してください。[する方法: .NET Framework のバージョンを対象とするアプリを構成する](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)です。  
  
 Version 1.0 または CLR では、Visual C でビルドしたアプリケーションのバージョン 1.1 で実行するのには、コンパイラを使用してコンパイルする必要があります[/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="see-also"></a>参照  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)