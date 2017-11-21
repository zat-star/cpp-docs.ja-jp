---
title: "ニーモニック (アクセス キー) を定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f19e255b2c8b63558dfe178ccfd7a23f8992861
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="defining-mnemonics-access-keys"></a>ニーモニック (アクセス キー) の定義
通常は、ユーザーがキーボード入力フォーカス間を移動 1 つのコントロール ダイアログ ボックスで、TAB キーと方向キーとします。 ただし、ユーザーを 1 つのキーを押して、コントロールを選択できるようにするアクセス キー (またはニーモニック覚えやすい名前) を定義することができます。  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>表示されるキャプション (プッシュ ボタン、チェック ボックス、およびオプション ボタン) を持つコントロールのアクセス キーを定義するには  
  
1.  ダイアログ ボックス コントロールを選択します。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)で、**キャプション**プロパティ、コントロールは、アンパサンドを入力する新しい名前を入力 (**&**) として設定文字の前に、そのコントロールのアクセス キー。 たとえば、`&Radio1` のようにします。  
  
3.  キーを押して**入力**です。  
  
     アクセス キーを示すために表示されるキャプションに下線が表示されます**R**adio1 です。  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>表示されるキャプションなしコントロールのアクセス キーを定義するには  
  
1.  使用して、コントロールのキャプションを加える、**静的テキスト**内の制御、[ツールボックス](/visualstudio/ide/reference/toolbox)です。  
  
2.  静的なテキスト キャプションのアンパサンドを入力します (**&**) アクセス キーとして設定文字の前にします。  
  
3.  静的なテキスト コントロールの直前に、タブ オーダーのラベルとなるコントロールを確認します。  
  
 ダイアログ ボックス内のすべてのアクセス キーは一意である必要があります。  
  
#### <a name="to-check-for-duplicate-access-keys"></a>重複するアクセス キーを確認するには  
  
1.  **形式** メニューのをクリックして**ニーモニックの確認**です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](https://msdn.microsoft.com/library/f45fce5x.aspx)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](https://msdn.microsoft.com/library/xbx3z216.aspx)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](https://msdn.microsoft.com/library/h6270d0z.aspx)です。  
  
### <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

