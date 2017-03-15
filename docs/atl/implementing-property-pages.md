---
title: "プロパティ ページの実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage クラス"
  - "IPropertyPage2 クラス"
  - "プロパティ ページ, 実装"
ms.assetid: 62f29440-33a7-40eb-a1ef-3634c95f640c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# プロパティ ページの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プロパティ ページは **IPropertyPage2** の `IPropertyPage` またはインターフェイスを実装する COM オブジェクトです。  ATL は [クラスの追加&#93;ダイアログ ボックス](../ide/add-class-dialog-box.md)の [&#91;ATL プロパティ ページ ウィザード&#93;](../atl/reference/atl-property-page-wizard.md) によってプロパティ ページの実装をサポートします。  
  
 プロパティ ページで、ATL を使用して作成するには:  
  
-   ATL ダイナミック リンク ライブラリの \(DLL\) サーバー プロジェクトを作成または開きます。  
  
-   [クラスのダイアログ ボックスを追加します。](../ide/add-class-dialog-box.md) を開き、**\[ATL プロパティ ページ\]**を選択します。  
  
-   \(ユーザー インターフェイスがあるため\)、プロパティ ページがマルチスレッド アパートメントであることを確認します。  
  
-   ページ内および関連付けられるドキュメントのタイトル、説明 \(文字列\)、およびヘルプ ファイルを設定します。  
  
-   、プロパティ ページのユーザー インターフェイスとして機能するに生成されたダイアログ リソースにコントロールを追加します。  
  
-   検証を実行する場合、ページのサイトを更新するには、のページに関連付けられているオブジェクトを更新するように、ページのユーザー インターフェイスの変更に応答します。  特に、プロパティ ページを変更するときに、呼び出し [IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)。  
  
-   オプションとして、次のガイドラインを参考にして `IPropertyPageImpl` メソッドをオーバーライドします。  
  
    |IPropertyPageImpl のメソッド|…する場合のオーバーライド|メモ|  
    |-----------------------------|-------------------|--------|  
    |[SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|サポートするインターフェイスと、ページに渡されるオブジェクトの数の基本的な正気のチェックを実行します。|基本クラスの実装を呼び出す前に独自のコードを実行します。  設定オブジェクトが予測に準拠しない場合、呼び出しはできるだけ早く失敗します。|  
    |[&#91;ライセンス認証&#93;](../Topic/IPropertyPageImpl::Activate.md)|ページのユーザー インターフェイスを初期化します。たとえば、オブジェクトから現在のプロパティの値を持つダイアログ コントロールを設定するか、コントロールを動的に作成することも、他の初期化を実行します\)。|これらを更新する前に、基本クラスにダイアログ ウィンドウを作成する前に、すべてのコントロールがあるように、コードの前に、基本クラスの実装を呼び出します。|  
    |[&#91;適用&#93;](../Topic/IPropertyPageImpl::Apply.md)|プロパティ設定を検証し、オブジェクトを更新します。|トレースとは何もしないため、呼び出し基本クラスの実装を呼び出す必要はありません。|  
    |[非アクティブ化](../Topic/IPropertyPageImpl::Deactivate.md)|関連ウィンドウの項目を削除します。|基本クラスの実装は、プロパティ ページを表すダイアログ ボックスを破棄します。  ダイアログ ボックスが破棄される前に、クリーンアップする必要がある場合は、基本クラスを呼び出す前にコードを追加する必要があります。|  
  
 例のプロパティ ページの実装については、[例: プロパティ ページの実装](../atl/example-implementing-a-property-page.md)を参照してください。  
  
> [!NOTE]
>  、プロパティ ページの ActiveX コントロールをホストする場合は、ウィザード生成されたクラスの派生を変更する必要があります。  基本クラスのリストに **CAxDialogImplCYourClass** と **CDialogImplCYourClass** を置き換えます。  
  
## 参照  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [ATLPages サンプル](../top/visual-cpp-samples.md)