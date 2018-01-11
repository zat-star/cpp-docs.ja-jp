---
title: "既存のコードから新しいプロジェクトのデバッグ設定 (Visual C) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.importwiz.debugsettings
dev_langs: C++
ms.assetid: 607339a8-9d33-458b-8095-dc73f374e29d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec7d357d53cb93ad5ba81c02fc3ccf1931cdd1cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="specify-debug-configuration-settings-create-new-project-from-existing-code-files-wizard"></a>[デバッグ構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)
既存コード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用すると、デバッグ構成のプロジェクト設定を指定できます。  
  
## <a name="task-list"></a>タスク一覧  
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コマンド ライン ビルドします。**  
 新規プロジェクトをビルドするコマンドラインを指定します。 たとえば、コンパイラ (すべてのスイッチと引数) の名前を入力するか、ビルド スクリプトを使用して、新しいプロジェクトをビルドすることです。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページです。 それ以外の場合は使用できません。  
  
 **コマンドラインを再構築します。**  
 新しいプロジェクトをリビルドするコマンドラインを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページです。 それ以外の場合は使用できません。  
  
 **クリーン コマンドライン**  
 新しいプロジェクトのビルド ツールによって生成されたサポート ファイルを削除するためのコマンドラインを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページです。 それ以外の場合は使用できません。  
  
 **出力 (デバッグ用)**  
 新しいプロジェクトのデバッグ構成の出力ファイルのディレクトリ パスを指定します。 このオプションが有効になっているときに、**を使用して外部のビルド システム**オプションがオン、**プロジェクト設定の指定**ページです。 それ以外の場合は使用できません。  
  
 **プリプロセッサの定義 (/D)**  
 新しいプロジェクトのプリプロセッサ シンボルを定義します。 詳細については、「 [/D (Preprocessor Definitions)](../build/reference/d-preprocessor-definitions.md)」を参照してください。  
  
 **検索パスを含める (/I)**  
 新しいプロジェクトのプリプロセッサ ディレクティブに渡されたファイル参照を解決するのには、コンパイラによって検索されるディレクトリの一覧に追加するディレクトリ パスを指定します。 詳細については、「[/I (追加インクルード ディレクトリ)](../build/reference/i-additional-include-directories.md)」を参照してください。  
  
 **強制インクルード ファイル (/FI)**  
 新しいプロジェクトをビルド時にヘッダー ファイルを指定します。 詳細については、「[/FI (強制インクルード ファイルの名前の指定)](../build/reference/fi-name-forced-include-file.md)」を参照してください。  
  
 **.NET アセンブリ検索パス (/AI)**  
 新しいプロジェクトのプリプロセッサ ディレクティブに渡される .NET アセンブリの参照を解決するのには、コンパイラによって検索されるディレクトリのパスを指定します。 詳細については、「[/AI (メタデータ ディレクトリの指定)](../build/reference/ai-specify-metadata-directories.md)」を参照してください。  
  
 **.NET アセンブリを使用して強制的に (/FU)**  
 新しいプロジェクトをビルド時に .NET アセンブリを指定します。 詳細については、「[/FU (強制 #using ファイルの名前の指定)](../build/reference/fu-name-forced-hash-using-file.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-project-settings-create-new-project-from-existing-code-files-wizard.md)
