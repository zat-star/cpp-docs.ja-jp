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
ms.openlocfilehash: a5036aa329c0b4004bd7ada724c62e1a1669f050
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)