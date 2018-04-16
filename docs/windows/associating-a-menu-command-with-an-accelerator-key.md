---
title: "メニュー コマンドをアクセラレータ キーに関連付ける |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79a16cf8d67fb7a6a45043c28455a7ed22f90ffa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>メニュー コマンドとアクセラレータ キーの関連付け
メニュー コマンドとキーボードの組み合わせで同じプログラム コマンドを発行したいと思うことはよくあります。 これを行うには、メニュー エディターを使用して、メニュー コマンドと、アプリケーションのアクセラレータ テーブル内のエントリに、同じリソース識別子を割り当てます。 次に、メニュー コマンドの [キャプション](../windows/menu-command-properties.md) を編集して、アクセラレータ キーの名前を表示します。  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>メニュー コマンドをアクセラレータ キーと関連付けるには  
  
1.  **メニュー** エディターで、目的のメニュー コマンドを選択します。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)で、アクセラレータ キーの名前を **キャプション** プロパティに追加します。  
  
    -   メニューのキャプションに続いて、タブ (\t) のエスケープ シーケンスを入力し、すべてのメニューのアクセラレータ キーが左揃えされるようにします。  
  
    -   修飾キー (**CTRL**, **ALT**, または **SHIFT**)、およびそれに続いて正符号 (**+**) と、追加キーの名前、文字、またはシンボルを入力します。  
  
         たとえば、 **CTRL+O** を **[ファイル]** メニューの **[開く]** コマンドに割り当てるには、メニュー コマンドの **キャプション** を変更し、次のようにします。  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         メニュー エディターのメニュー コマンドは、入力する新しいキャプションを反映するよう更新されます。  
  
3.  [アクセラレータ](../windows/adding-an-entry-to-an-accelerator-table.md) エディターで **アクセラレータ テーブル エントリ** を作成し、メニュー コマンドと同じ識別子をそれに割り当てます。 使用するキーの組み合わせは、覚えやすいものにしてください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [メニューにコマンドを追加します。](../windows/adding-commands-to-a-menu.md)   
 [メニュー エディター](../windows/menu-editor.md)