---
title: "COM インターフェイスの作成 (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.com.creating.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM インターフェイス, 作成"
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM インターフェイスの作成 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ には、COM オブジェクトとオートメーション クラスのための COM インターフェイス定義と COM ディスパッチ インターフェイス定義を使用する、プロジェクト作成用のウィザードとテンプレートが用意されています。  
  
 これらのウィザードを使用して、以下の 3 つの一般的なタスクを実行できます。  
  
-   [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用して MFC プロジェクトを作成した後で、MFC に ATL サポートを追加 コード ウィザードを実行してプロジェクトに ATL サポートを追加します。  このサポートの適用対象は、MFC の実行可能ファイルまたは DLL プロジェクトに追加された単純な COM オブジェクトだけです。  これらの ATL オブジェクトには複数のインターフェイスが含まれることがあります。  
  
-   [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)を開き、.idl ファイルで定義されたディスパッチ インターフェイスとコントロール クラスで定義されたイベント マップを持つ ActiveX コントロールを作成します。  
  
-   [ATL コントロールの追加](../atl/reference/adding-an-atl-control.md)  
  
     [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)および [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)を使用して、ATL ActiveX コントロールを作成します。  
  
     また、ATL サポートを追加した MFC プロジェクトに ATL コントロールを追加することもできます。  ATL サポートを MFC プロジェクトに追加していない状態で \[クラスの追加\] ダイアログ ボックスの **\[ATL コントロール\]** を選択すると、ATL サポートを MFC プロジェクトに追加するかどうかを確認するダイアログ ボックスが表示されます。  
  
     このウィザードは、プロジェクト クラスに IDL ソースと COM マップを生成します。  
  
 ATL プロジェクトを開くと、[&#91;クラスの追加&#93;](../ide/add-class-dialog-box.md) ダイアログ ボックスで、COM インターフェイスをプロジェクトに追加するほかのウィザードとテンプレートを選択できます。  以下のウィザードを使用すると、オブジェクトに 1 つ以上のインターフェイスを設定できます。  
  
-   [ATL COM\+ 1.0 コンポーネント ウィザード](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)  
  
-   [ATL Active Server Pages コンポーネント ウィザード](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)  
  
 また、クラス ビューでオブジェクトのコントロール クラスを右クリックし、[&#91;インターフェイスの実装&#93;](../Topic/Implement%20Interface%20Wizard.md) をクリックすると、COM コントロールに新しいインターフェイスを実装できます。  
  
> [!NOTE]
>  Visual Studio には、プロジェクトにインターフェイスを追加するウィザードはありません。  [ATL シンプル オブジェクト ウィザード](../atl/reference/atl-simple-object-wizard.md)を使用してシンプル オブジェクトを追加することで、ATL プロジェクトにインターフェイスを追加したり、[MFC プロジェクトに ATL サポートを追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)したりできます。  または、プロジェクトの .idl ファイルを開き、次のように入力してインターフェイスを作成します。  
  
```  
interface IMyInterface {  
};  
  
```  
  
 詳細については、「[インターフェイスの実装](../ide/implementing-an-interface-visual-cpp.md)」および「[ATL プロジェクトへのオブジェクトとコントロールの追加](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)」を参照してください。  
  
 Visual C\+\+ には、プロジェクトに対して定義した [COM インターフェイスを編集](../ide/editing-a-com-interface.md)および表示するいくつかの方法があります。  [クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925) には、C\+\+ プロジェクトの .idl ファイルで定義されているインターフェイスまたはディスパッチ インターフェイスのアイコンが表示されます。  
  
 ATL ベースの COM オブジェクト クラスの場合、クラス ビューには ATL クラスの COM マップが読み込まれ、ATL クラスと ATL クラスが実装する各インターフェイスとの関係が表示されます。  
  
 クラス ビューとそのショートカット メニューでは、以下の方法でインターフェイスを処理できます。  
  
-   ATL オブジェクトを MFC ベースのアプリケーションに追加する。  
  
-   メソッド、プロパティ、およびイベントを追加する。  
  
-   アイテムをダブルクリックして、項目のインターフェイス コードに直接移動する。  
  
## 参照  
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)