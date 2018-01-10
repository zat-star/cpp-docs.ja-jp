---
title: "カスタム ビルド ステップとビルド イベントを理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- builds [C++], events
- custom build steps [C++], customizing builds
- events [C++], build
- custom build steps [C++]
- build steps [C++]
- build events [C++], order of events and build steps
- build steps [C++], build events
- builds [C++], custom build steps
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9abb7ff0b9a39656999e7a53b476056f7a5b1558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-custom-build-steps-and-build-events"></a>カスタム ビルド ステップとビルド イベントについて
Visual C 開発環境で、次の 3 つ基本的な方法はビルド プロセスをカスタマイズします。  
  
 **カスタム ビルド ステップ**  
 カスタム ビルド ステップは、プロジェクトに関連付けられているビルド ルールです。 カスタム ビルド ステップでは、追加の入力または出力ファイル、および表示するメッセージを実行するコマンドラインを指定できます。 詳細については、次を参照してください。[する方法: MSBuild プロジェクトにカスタム ビルド ステップを追加](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)です。  
  
 **カスタム ビルド ツール**  
 カスタム ビルド ツールは、1 つまたは複数のファイルに関連付けられているビルド ルールです。 カスタム ビルド ステップは、カスタム ビルド ツールは、結果、1 つに入力ファイルを渡すことができます、または以上の出力ファイル。 たとえば、MFC アプリケーションのヘルプ ファイルは、カスタム ビルド ツールを使用して構築されます。 詳細については、次を参照してください。[する方法: MSBuild プロジェクトへのカスタム ビルド ツールの追加](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)と[を指定するカスタム ビルド ツール](../ide/specifying-custom-build-tools.md)です。  
  
 **ビルド イベント**  
 ビルド イベントを使用して、プロジェクトのビルドをカスタマイズできます。 3 つのビルド イベントがある:*ビルド前*、 *pre-link*、および*ビルド後*です。 ビルド イベントを使用して、ビルド プロセスで特定の時点で発生するアクションを指定できます。 たとえば、ビルド イベントを使用してファイルを登録するでした**regsvr32.exe**プロジェクトのビルドが完了した後です。 詳細については、次を参照してください。[ビルド イベントの指定](../ide/specifying-build-events.md)です。  
  
 [ビルドのカスタマイズのトラブルシューティング](../ide/troubleshooting-build-customizations.md)カスタム ビルド ステップすることを確認して、ビルド イベントが想定どおりに実行できます。  
  
 カスタムの出力形式のビルド ステップまたはビルド イベントは、ツールの操作性を強化できますも。 詳細については、「[カスタム ビルド ステップまたはビルド イベントの出力の書式設定](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md)」を参照してください。  
  
 ビルド イベントとカスタム ビルドの他のビルド手順と共に次の順序で実行する手順を。  
  
1.  ビルド前イベント  
  
2.  個々 のファイルに対するカスタム ビルド ツール  
  
3.  MIDL  
  
4.  リソース コンパイラ  
  
5.  C と C++ コンパイラ  
  
6.  Pre-Link イベント  
  
7.  リンカー、ライブラリアン (必要に応じて) または  
  
8.  マニフェスト ツール  
  
9. BSCMake  
  
10. プロジェクトでカスタム ビルド ステップ  
  
11. ビルド後のイベント  
  
 `custom build step on the project`と`post-build event`他のすべてのビルド後に順番に実行が完了を処理します。  
  
## <a name="see-also"></a>参照  
 [Visual Studio での C++ プロジェクトのビルド](../ide/building-cpp-projects-in-visual-studio.md)   
 [ビルドのコマンドとプロパティの共通のマクロ](../ide/common-macros-for-build-commands-and-properties.md)   
 [ツールのビルド順序 ダイアログ ボックス](http://msdn.microsoft.com/en-us/6204c5b1-7ce9-4948-9ff6-0268642ee14c)