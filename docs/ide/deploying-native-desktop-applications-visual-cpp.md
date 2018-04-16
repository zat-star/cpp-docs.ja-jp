---
title: "ネイティブ デスクトップ アプリケーション (Visual C) の配置 |Microsoft ドキュメント"
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
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fe88a322314ac24fa5799735e84ff100efa2e79
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="deploying-native-desktop-applications-visual-c"></a>ネイティブ デスクトップ アプリケーションの配置 (Visual C++)
配置とは、完成したアプリケーションやコンポーネントを他のコンピューターにインストールできるように配布するためのプロセスです。 配置計画は、開発者のコンピューターでアプリケーションが作成されたときから始まります。 そのアプリケーションがユーザーのコンピューターにインストールされ、使用できるようになったときに、配置は終了します。  
  
 Visual Studio は、Windows アプリケーションを配置するためのさまざまなテクノロジを提供しています。 ClickOnce 配置と Windows インストーラーの展開が含まれます。  
  
-   共通言語ランタイム (CLR) を対象とする C++ アプリケーションの配置に ClickOnce を使用できる、混合、純粋、および検証可能なアセンブリ。 マネージ アプリケーションを展開する Windows インストーラーを使用できますが、マニフェスト署名などの .NET Framework のセキュリティ機能の活用しているために、ClickOnce を使用することをお勧めします。 ClickOnce では、ネイティブ C++ アプリケーションの展開はサポートされません。 詳細については、「 [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md)」を参照してください。  
  
-   Windows インストーラー テクノロジは、ネイティブ C++ アプリケーションに使用することも、CLR を対象とする C++ アプリケーションに使用することもできます。  
  
 このドキュメントのこのセクションの記事では、ネイティブ Visual C++ アプリケーションをあらゆるコンピューターで確実に実行する方法について説明するために、サポート対象のターゲット プラットフォーム、インストール パッケージに含める必要があるファイル、アプリケーションに依存するコンポーネントの推奨される再配布方法を示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Visual C++ での配置](../ide/deployment-in-visual-cpp.md)  
  
 [配置の概念](../ide/deployment-concepts.md)  
  
 [Visual C++ アプリケーションの依存関係の理解](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)  
  
 [再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md)  
  
 [配置方法の選択](../ide/choosing-a-deployment-method.md)  
  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)  
  
 [配置例](../ide/deployment-examples.md)  
  
 [Web クライアント アプリケーションの再頒布](../ide/redistributing-web-client-applications.md)  
  
 [Visual C++ アプリケーションの ClickOnce 配置](../ide/clickonce-deployment-for-visual-cpp-applications.md)  
  
 [以前のランタイム バージョンでの C++/clr アプリケーションを実行しています。](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)  
  
## <a name="related-sections"></a>関連項目  
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
 [配置](/dotnet/framework/deployment/index)  
  
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのトラブルシューティング](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)