---
title: "メニュー コマンドに対するアクセス キーの割り当て |Microsoft ドキュメント"
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
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccf64739d0a54b5a96551b3a8145dc3c3f8378c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="assigning-access-keys-to-menu-commands"></a>メニュー コマンドに対するアクセス キーの割り当て
メニューとメニュー コマンドにアクセス キー (ユーザーがキーボードを使ってメニューを選択できるようにするニーモニック) を割り当てることができます。  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>メニュー コマンドにアクセス (ショートカット) キーを割り当てるには  
  
1.  メニュー名やコマンド名の文字の前にアンパサンド (**&**) を入力し、対応するアクセス キーとしてその文字を指定します。 たとえば、"&File" は ALT+F を、Microsoft Windows で作成されるアプリケーションの [File] メニューのショートカット キーとして設定します。  
  
     メニュー項目は、文字の 1 つがショートカット キーに割り当てられている表示可能キューを提供します。 アンパーサンドに続く文字は、下線付きで表示されます (オペレーティング システムによって異なる)。  
  
    > [!NOTE]
    >  メニューを右クリックし、ショートカット メニューから **[ニーモニックの確認]** を選択して、メニューのすべてのアクセスキーが一意であることを確認してください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 必要条件  
  
 Win32  
  
## <a name="see-also"></a>参照  
 [メニュー エディター](../windows/menu-editor.md)