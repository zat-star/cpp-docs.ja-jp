---
title: "動的レイアウト | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 8598cfb2-c8d4-4f5a-bf2b-59dc4653e042
caps.latest.revision: 7
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 動的レイアウト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] の MFC では、ユーザーがサイズ変更できるダイアログを作成でき、サイズ変更に合わせてレイアウトを調整する方法を制御することができます。  たとえば、ボタンをダイアログの下の端に付けて、常にダイアログ ボックスの下部に配置されるようにすることができます。  ユーザーがダイアログを展開するときに、リスト ボックス、エディット ボックス、テキスト フィールドなどの特定のコントロールを展開するように設定することもできます。  
  
## MFC ダイアログ ボックスのレイアウトの動的な設定を指定する  
 ユーザーがダイアログ ボックスをサイズ変更するときに、ダイアログのコントロールのサイズを変更したり、X と Y の方向に移動したりできます。  ユーザーがダイアログ ボックスのサイズを変更するときのコントロールのサイズや位置の変更は、動的レイアウトと呼ばれます。  たとえば、次に示すのはサイズを変更する前のダイアログです。  
  
 ![サイズ変更する前のダイアログ。](../mfc/media/mfcdynamiclayout4.png "MFCDynamicLayout4")  
  
 サイズを変更した後で、リスト ボックス領域がより多くの項目を表示するよう増え、ボタンは右下隅に沿って移動します。  
  
 ![サイズ変更した後のダイアログ。](../mfc/media/mfcdynamiclayout5.png "MFCDynamicLayout5")  
  
 IDE のリソース エディターの各コントロールの詳細を指定して、動的レイアウトを制御することも、特定のコントロールの CMFCDynamicLayout オブジェクトにアクセスしてプロパティを設定し、プログラムで制御することもできます。  
  
### リソース エディターで動的レイアウト プロパティを設定する  
 リソース エディターを使用すると、コードを記述しなくても、ダイアログ ボックス動的のレイアウトの動作を設定できます。  
  
##### 動的レイアウトのプロパティをリソース エディターで設定するには  
  
1.  MFC プロジェクトを開いた状態にして、ダイアログ エディターで作業するダイアログ ボックスを開きます。  
  
     ![リソース エディターのダイアログを開きます。](../mfc/media/mfcdynamiclayout3.png "MFCDynamicLayout3")  
  
2.  コントロールを選択し、\[プロパティ\] ウィンドウで、その動的レイアウト プロパティを設定します。  \[プロパティ\] ウィンドウの **\[動的レイアウト\]** セクションには、**\[型の移動\]**、**\[サイズ変更の種類\]** のプロパティが含まれ、これらのプロパティに対して選択した値に応じて、コントロールを移動またはサイズを変更する方法を定義する固有のプロパティが含まれます。  **\[型の移動\]** は、ダイアログのサイズ変更に合わせてコントロールを移動する方法を決定し、**\[サイズ変更の種類\]** は、ダイアログのサイズの変更に合わせてコントロールがサイズ変更される方法を決定します。  **\[型の移動\]** と **\[サイズ変更の種類\]** は、動的に変更したい方向に応じて、**\[水平\]**、**\[垂直\]**、**\[両方\]**、または **\[なし\]** になります。  \[水平\] は X 方向、\[垂直\] はY 方向です。  
  
3.  **\[OK\]** または **\[キャンセル\]** ボタンに一般的である、ボタンなどのコントロールを固定サイズにして、右下に配置したい場合は、**\[サイズ変更の種類\]** を **\[なし\]** に設定して**\[移動の種類\]** を **\[両方\]** に設定します。  **\[移動の種類\]** の下の **\[X の移動\]** と **\[Y の移動\]** の値には 100% を設定して、コントロールが右下隅から一定の距離を維持するようにします。  
  
     ![動的レイアウト](../mfc/media/mfcdynamiclayout1.png "MFCDynamicLayout1")  
  
4.  ダイアログ ボックスの拡張と共に拡張させたいコントロールがあるとします。  通常、複数行の編集ボックスを拡張して、テキスト領域のサイズを増やすために、ダイアログを拡張するか、より多くのデータを表示するために、リスト コントロールを拡張します。  この場合、**\[サイズ変更の種類\]** を \[両方\] に設定して、**\[移動の種類\]** を \[なし\] にします。  次に、**\[X のサイズ変更\]** と **\[Y のサイズ変更\]** の値を 100 に設定します。  
  
     ![動的レイアウト設定](../mfc/media/mfcdynamiclayout2.png "MFCDynamicLayout2")  
  
5.  コントロールにとって意味がある可能性のあるその他の値をテストします。  たとえば、1 行のテキスト ボックスを持つダイアログで、**\[サイズ変更の種類\]** を **\[水平\]** のみに設定するとします。  
  
### プログラムによる動的レイアウト プロパティの設定  
 前の手順は、デザイン時にダイアログの動的レイアウト プロパティを指定するには便利ですが、動的レイアウト プロパティを実行時に制御したい場合は、動的レイアウト プロパティをプログラムで設定できます。  
  
##### 動的レイアウト プロパティをプログラムによって設定するには  
  
1.  ダイアログの動的レイアウトを指定する、ダイアログ クラスの実装コードの場所を検索または作成します。  たとえば、ダイアログに `AdjustLayout` などのメソッドを追加して、レイアウトを変更する必要がある場所から呼び出すことができます。  最初にこれをコンストラクターから呼び出すか、ダイアログに変更を加えた後で呼び出すことができます。  
  
2.  ダイアログで CWnd クラスのメソッドである [GetDynamicLayout](../Topic/CWnd::GetDynamicLayout.md) を呼び出します。  GetDynamicLayout は、CMFCDynamicLayout オブジェクトへのポインターを返します。  
  
    ```  
    CMFCDynamicLayout* dynamicLayout = pDialog->GetDynamicLayout();  
    ```  
  
3.  動的な動作を追加する最初のコントロールでは、動的レイアウト クラスで静的メソッドを使用して、コントロールを調整する方法をエンコードする [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 構造体を作成します。  最初に、[CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md)、[CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md)、[CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md)、または [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md) の適切な静的メソッドを選択してこれを行います。  移動の水平\/垂直方向のアスペクト比率を渡します。  これらすべての静的メソッドは、コントロールの移動の動作を指定する時に使用できる、新しく作成された MoveSettings オブジェクトを返します。  
  
     100 にするとダイアログのサイズ変更とまったく同じサイズの移動を行い、これによりコントロールのエッジが新しい境界からの固定距離を維持します。  
  
    ```  
    MoveSettings moveSettings = CMFCDynamicLayout::MoveHorizontal(100);  
    ```  
  
4.  サイズの動作について、[SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 型を使用して同じ操作を行います。  たとえば、ダイアログ ボックスのサイズを変更するときにコントロールがサイズを変更しないよう指定するには、次のコードを使用します。  
  
    ```  
    SizeSettings sizeSettings = CMFCDynamicLayout::SizeNone();  
    ```  
  
5.  [CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md) メソッドを使用して、コントロールを動的レイアウト マネージャーに追加します。  目的のコントロールを指定するさまざまな方法に対して、2 つのオーバーロードがあります。  1 つはコントロールのウィンドウ ハンドル \(HWND\) を取得し、もう 1 つは、コントロールの ID を取得します。  
  
    ```  
    dynamicLayout->AddItem(hWndControl, moveSettings, sizeSettings);  
    ```  
  
6.  移動またはサイズを変更する必要がある各コントロールに対して繰り返します。  
  
7.  必要に応じて、コントロールがすでに動的レイアウトの変更の対象となるコントロールのリスト上にあるか判断するために [CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md) メソッドを使用することも、変更の対象となっているすべてのコントロールがあるかどうかを判断するために [CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md) メソッドを使用することもできます。  
  
8.  ダイアログのレイアウトを有効にするには [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md) メソッドを呼び出します。  
  
    ```  
    pDialog->EnableDynamicLayout(TRUE);  
    ```  
  
9. 次回ユーザーがダイアログをサイズ変更するときに、[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md) メソッドが呼び出され、実際に設定を適用します。  
  
10. 動的レイアウトを無効にする場合は、`bEnabled` パラメーターに `FALSE` を指定した [CWnd::EnableDynamicLayout](../Topic/CWnd::EnableDynamicLayout.md) を呼び出します。  
  
    ```  
    pDialog->EnableDynamicLayout(FALSE);  
    ```  
  
##### リソース ファイルから動的レイアウトをプログラムで設定するには  
  
1.  [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md) メソッドを使用して、次の例のように、動的レイアウトの情報を指定する、関連するリソース スクリプト ファイル \(.rc ファイル\) で、リソース名を指定します。  
  
    ```  
    dynamicLayout->LoadResource("IDD_DIALOG1");  
    ```  
  
     名前付きのリソースは、次の例のように、リソース ファイル内の AFX\_DIALOG\_LAYOUT エントリの形式のレイアウト情報が含まれているダイアログを参照する必要があります。  
  
    ```  
    /////////////////////////////////////////////////////////////////////////////  
    //  
    // AFX_DIALOG_LAYOUT  
    //  
  
    IDD_MFCAPPLICATION1_DIALOG AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6400, 0x0028, 0x643c, 0x0028  
    END  
  
    IDD_DIALOG1 AFX_DIALOG_LAYOUT  
    BEGIN  
        0x0000, 0x6464, 0x0000, 0x6464, 0x0000, 0x0000, 0x6464, 0x0000, 0x0000  
  
    END  
    ```  
  
## 参照  
 [CMFCDynamicLayout クラス](../mfc/reference/cmfcdynamiclayout-class.md)   
 [コントロール クラス](../mfc/control-classes.md)   
 [ダイアログ ボックス クラス](../mfc/dialog-box-classes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)