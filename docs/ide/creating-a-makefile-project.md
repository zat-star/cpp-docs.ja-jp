---
title: "メイクファイル プロジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.makefile.project
dev_langs: C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 834475840fbe20a0d6938c563f3541c294e09bee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-makefile-project"></a>メイクファイル プロジェクトの作成
メイクファイルを使用してコマンド ラインからビルドしたプロジェクトは、Visual Studio 開発環境では認識されません。 開き、使用して、プロジェクトをビルドする[!INCLUDE[vsUltShort](../ide/includes/vsultshort_md.md)]、メイクファイル プロジェクト テンプレートを選択して、空のプロジェクトをまず作成 Visual Studio Professional、または Visual Studio Express for Windows Desktop、します。 作成した空のプロジェクトを使用して、目的のプロジェクトを Visual Studio 開発環境でビルドします。  
  
 ソリューション エクスプローラーでは、プロジェクトのファイルは表示されません。 プロジェクトで指定したビルド構成は、プロジェクトのプロパティ ページに反映されます。  
  
 プロジェクトで指定した出力ファイルは、ビルド スクリプトの生成するファイルの名前には直接は影響しません。  
  
### <a name="to-create-a-makefile-project"></a>メイクファイル プロジェクトを作成するには  
  
1.  ヘルプ トピックの指示に従って、 [Visual C のアプリケーション ウィザードでプロジェクトを作成する](../ide/creating-desktop-projects-by-using-application-wizards.md)です。  
  
2.  **新しいプロジェクト**ダイアログ ボックスで、**メイクファイル プロジェクト**を開くには、ウィザードの [テンプレート] ペインでします。  
  
3.  [アプリケーション設定](../ide/application-settings-makefile-project-wizard.md)ページ、コマンドを入力、出力、クリーンアップ、および情報を再構築します。  
  
4.  をクリックして**完了**、ウィザードを終了しで新しく作成されたプロジェクトを開く**ソリューション エクスプ ローラー**です。  
  
 プロジェクトのプロパティは、プロパティ ページで表示および編集できます。 参照してください[Visual C プロジェクトのプロパティの設定](../ide/working-with-project-properties.md)については、プロパティ ページを表示します。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイル プロジェクト ウィザード](../ide/makefile-project-wizard.md)   
 [メイクファイルの特殊文字](../build/special-characters-in-a-makefile.md)   
 [メイクファイルの内容](../build/contents-of-a-makefile.md)