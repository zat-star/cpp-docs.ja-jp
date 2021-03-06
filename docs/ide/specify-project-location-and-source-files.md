---
title: 新しいコード プロジェクトを既存のソース ファイル (Visual C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vc.appwiz.importwiz.location
dev_langs:
- C++
ms.assetid: 29ddffb9-5918-4d72-8c7a-a365f9de96dd
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04f73f89745f797658029eac2331d1764af4c065
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="specify-project-location-and-source-files-create-new-project-from-existing-code-files-wizard"></a>[プロジェクトの場所とソース ファイルの指定] \(既存コード ファイルからの新しいプロジェクトの作成ウィザード)
指定するには、既存のコード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用します。  
  
-   新しいプロジェクトのディレクトリ パス。  
  
-   既存のソース ファイルを検索するディレクトリ  
  
-   ウィザードで新しいプロジェクトにインポートされるファイルの種類  
  
## <a name="task-list"></a>タスク一覧  
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **プロジェクト ファイルの場所**  
 新しいプロジェクトのディレクトリ パスを指定します。 新しいプロジェクトのすべてのファイル (およびサブディレクトリ) は、この位置に格納されます。  
  
 **参照**  
 表示、**プロジェクト ファイルの場所**ダイアログで、新しいプロジェクトを格納するディレクトリを指定できます。 このコントロールでは、目的のフォルダーに移動することができます。  
  
 **プロジェクト名**  
 新しいプロジェクトの名前を指定します。 .Vcxproj などのファイル拡張子を持つプロジェクト ファイルは、この名前に適用されます。 既存のコード ファイルでは、元の名前を保持します。  
  
 **これらのフォルダーからファイルをプロジェクトに追加します。**  
 オンにした場合は、新しいプロジェクトが元のディレクトリ (このコントロール下にあるリスト ボックスで指定) から既存のコード ファイルをコピーするウィザードを設定します。  
  
 **サブフォルダーを追加します。**  
 一覧表示、ディレクトリのすべてのサブディレクトリからコード ファイルをコピーするように指定**フォルダー**列、新しいプロジェクトに挿入します。  
  
 **フォルダー**  
 新しいプロジェクトにコピーする既存のコード ファイルを含むディレクトリへのパスを示します。 この列は、既存のコード ファイルを検索するすべてのディレクトリを一覧表示します。  
  
 **[追加]**  
 表示、**このフォルダーからファイルをプロジェクトに追加** ダイアログ ボックスは、ウィザードは既存のコード ファイルを検索するディレクトリを指定することができます。  
  
 **削除**  
 このコントロールのリスト ボックスの左側で選択されているディレクトリのパスを削除します。  
  
 **プロジェクトに追加するファイルの種類**  
 指定されたファイル拡張子を基に新しいプロジェクトに、ウィザードを追加するファイルの種類を指定します。 ファイル拡張子は、アスタリスクのワイルドカード文字が付きます。 とはファイル拡張子の一覧で、セミコロンで区切られます。  
  
 **ソリューション エクスプ ローラーですべてのファイルを表示します。**  
 新しいプロジェクトに参照および表示にするソリューション エクスプ ローラー ウィンドウのすべてのファイルを指定します。 既定では、このオプションは有効になっています。