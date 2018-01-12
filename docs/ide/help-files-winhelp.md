---
title: "ヘルプ ファイル (WinHelp) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5698f7001512c5a4f8c45b5c787f35c9ce0ca6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="help-files-winhelp"></a>ヘルプ ファイル (WinHelp)
選択して、アプリケーションにヘルプのサポートの WinHelp の種類を追加するときに、次のファイルが作成された、**状況依存のヘルプ** チェック ボックスをクリックして**WinHelp 形式**で[高度な機能](../mfc/reference/advanced-features-mfc-application-wizard.md)MFC アプリケーション ウィザードのページです。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|ヘルプ コンパイラで、プログラムまたはコントロールのヘルプ ファイルを作成するために使用するヘルプ プロジェクト ファイル。|  
|*Projname*.rtf|*Projname*\hlp|ヘルプ ファイル|編集可能なテンプレート トピックや、.hpj ファイルをカスタマイズする方法の情報が含まれています。|  
|*Projname*.cnt|*Projname*\hlp|ヘルプ ファイル|構造を提供、**内容**Windows ヘルプ ウィンドウです。|  
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトがコンパイルされるときにヘルプ プロジェクトをビルドするシステムで使用します。|  
|Print.rtf|*Projname*\hlp|ヘルプ ファイル|プロジェクトには、印刷のサポート (既定) が含まれている場合に作成されます。 印刷コマンドとダイアログ ボックスについて説明します。|  
|*.bmp|*Projname*\hlp|リソース ファイル (Visual Studio)|生成されたヘルプ トピックについてはファイルのイメージが含まれます。|  
  
 MFC ActiveX コントロール プロジェクトに WinHelp サポートを追加するには を選択して**ヘルプ ファイルの生成**で、[アプリケーション設定](../mfc/reference/application-settings-mfc-activex-control-wizard.md)MFC ActiveX コントロール ウィザードのタブ。 次のファイルは、MFC ActiveX コントロールへのヘルプのサポートを追加すると、プロジェクトに追加されます。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|説明|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Projname*.hpj|*Projname*\hlp|ソース ファイル|ヘルプ コンパイラで、プログラムまたはコントロールのヘルプ ファイルを作成するために使用するプロジェクト ファイルです。|  
|*Projname*.rtf|*Projname*\hlp|プロジェクト|編集可能なテンプレート トピックや、.hpj ファイルをカスタマイズする方法の情報が含まれています。|  
|Makehelp.bat|*Projname*|ソース ファイル|プロジェクトがコンパイルされるときにヘルプ プロジェクトをビルドするシステムで使用します。|  
|Bullet.bmp|*Projname*|リソース ファイル (Visual Studio)|箇条書きリストを表すために標準のヘルプ ファイルのトピックで使用します。|  
  
## <a name="see-also"></a>参照  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)