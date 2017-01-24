---
title: "MFC ActiveX コントロール : 高度なトピック | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireError メソッド"
  - "MFC ActiveX コントロール, アクセス (表示されないダイアログ コントロールに)"
  - "MFC ActiveX コントロール, 高度なトピック"
  - "MFC ActiveX コントロール, データベース クラス"
  - "MFC ActiveX コントロール, エラー コード"
  - "MFC ActiveX コントロール, パラメーター化されたプロパティ"
  - "MFC ActiveX コントロール, 特殊キー"
  - "PreTranslateMessage メソッド"
  - "ThrowError メソッド"
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : 高度なトピック
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ActiveX コントロールを開発する場合の高度なトピックについて説明します。  次にその例を示します。  
  
-   [ActiveX コントロールのデータベース クラスを使用します。](#_core_using_database_classes_in_activex_controls)  
  
-   [パラメーター化されたプロパティの実装](#_core_implementing_a_parameterized_property)  
  
-   [ActiveX コントロールの Handling Errors](#_core_handling_errors_in_your_activex_control)  
  
-   [コントロールの処理の特殊なキー](#_core_handling_special_keys_in_your_control)  
  
-   [実行時されないアクセス ダイアログ コントロール](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> ActiveX コントロールのデータベース クラスを使用します。  
 ActiveX コントロール クラスがクラス ライブラリの一部であるため、MFC データベース クラスを使用する ActiveX コントロールを開発する際に、標準の MFC アプリケーションのデータベース クラスを使用するための手順と規則を適用できます。  
  
 MFC データベース クラスの概要については、[MFC データベース クラス \(DAO と ODBC\)](../Topic/MFC%20Database%20Classes%20\(ODBC%20and%20DAO\).md)を参照してください。  ここでは、MFC ODBC クラスと MFC DAO クラスの両方を紹介し、いずれかの詳細に指示します。  
  
> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  Microsoft は、新しいプロジェクトに [OLE DB テンプレート](../data/oledb/ole-db-programming.md) または [ODBC と MFC](../data/odbc/odbc-and-mfc.md) を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
##  <a name="_core_implementing_a_parameterized_property"></a> パラメーター化されたプロパティの実装  
 パラメーター化されたプロパティは、プロパティの配列 \(コンストラクター\) をコントロールのプロパティとして値の同種コレクションを公開するためのメソッドです。  たとえば、プロパティとして配列または辞書を公開するには、パラメーター化されたプロパティを使用できます。  Visual Basic では、このようなプロパティは配列表記を使用してアクセスされます:  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/VisualBasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 パラメーター化されたプロパティを実装するには、プロパティの追加ウィザードを使用します。  プロパティの追加ウィザードは、コントロールのユーザーが上の表記を使用してまたは標準スキームでプロパティにアクセスできるようにする Get または Set 関数のペアを追加してプロパティを実装します。  
  
 メソッドとプロパティのパラメーター化されたプロパティと同様に、許容されるパラメーターの数に制限がない。  パラメーター化されたプロパティは、制限が 15 のパラメーターで、プロパティ値を格納するために予約されて 1 個のパラメーターが\)。  
  
 次の手順では、整数の次元配列としてアクセスできる呼び出されるパラメーター化されたプロパティ配列を追加します。  
  
#### パラメーター化されたプロパティの追加ウィザードのプロパティを追加するには  
  
1.  コントロールのプロジェクトを読み込んでください。  
  
2.  クラス ビューで、コントロール ライブラリ ノードを展開します。  
  
3.  ショートカット メニューを表示するコントロール \(ライブラリ ノードの 2 番目のノード\) のインターフェイス ノードを右クリックします。  
  
4.  ショートカット メニューで、クリック **追加** は、**\[プロパティの追加\]** をクリックします。  
  
5.  **プロパティ名** ボックスで、`Array`を入力します。  
  
6.  **プロパティの種類** ボックスで、**short**を選択します。  
  
7.  **実装** の場合、クリック **Get\/Set メソッドの設定**。  
  
8.  **Get 関数\(G\)** と **関数の設定** ボックスで、型の一意の名前は Set 関数取得または既定の名前を受け入れます。  
  
9. **パラメータ名** と **パラメータの種類** のコントロールを使用して `row` \(型 `short`\) というパラメーターを追加します。  
  
10. 2 番目のパラメーターによって呼び出されます `column` \(型 `short`\) を追加します。  
  
11. \[完了\] をクリックします。  
  
### プロパティの追加ウィザードによる変更  
 カスタム プロパティを追加すると、プロパティの追加ウィザードはコントロール クラスのヘッダーを変更します。H\) と実装 \(.cpp\) ファイル。  
  
 次の行では、コントロール クラスに追加されます。H ファイル:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-topics_2.h)]  
  
 このコードは `GetArray` と `SetArray` というユーザーがプロパティにアクセスするときに特定の列と行を要求できるようにするには 2 とおりの関数を宣言します。  
  
 また、プロパティの追加ウィザードは、コントロール クラス実装 \(.cpp\) ファイルにあるコントロールのディスパッチ マップに次の行を追加する:  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 最後に、`GetArray` の実装と `SetArray` 関数は、.cpp ファイルの末尾に追加されます。  ほとんどの場合、プロパティの値を返すには、Get 関数を変更します。  Set 関数は、実行する必要のあるコードをプロパティの変更の前後のいずれかが含まれます。  
  
 便利です。このプロパティのパラメーター化されたプロパティの値を格納するコントロール クラスの次元配列のメンバー変数が、型 **short**の宣言できます。  そのパラメーターによって示されるように、適切な行と列に格納された値を返すには、Get 関数を変更する行と列パラメーターによって参照される値を更新するように Set 関数を変更します。  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> ActiveX コントロールの Handling Errors  
 エラー条件が発生すると、コントロールにコントロール コンテナーにエラーを通知する必要があります。  エラーが発生した場合に、エラーを報告するための 2 種類のメソッドがあります。  エラーがプロパティ内で発生したかまたは OLE オートメーションのメソッドの実装内の集約関数は、またはエラーが発生した場合に、コントロールのユーザーに通知 [COleControl::ThrowError](../Topic/COleControl::ThrowError.md)コントロールを呼び出す必要があります。  エラーが他の時に発生する、標準的なエラー イベントを発生させるコントロールは [COleControl::FireError](../Topic/COleControl::FireError.md)を呼び出す必要があります。  
  
 発生したエラーの種類を示すために、コントロールは `ThrowError` または `FireError`にエラー コードを渡す必要があります。  エラー コードは 32 ビット値を持つ OLE ステータス コードです。  可能な場合は、OLECTL.H のヘッダー ファイルで定義されたコードの標準セットからエラー コードをクリックします。  次の表は、これらのコードを示します。  
  
### ActiveX コントロールのエラー コード  
  
|エラー|説明|  
|---------|--------|  
|**CTL\_E\_ILLEGALFUNCTIONCALL**|無効な関数呼び出し|  
|**CTL\_E\_OVERFLOW**|オーバーフロー|  
|**CTL\_E\_OUTOFMEMORY**|メモリが足りません|  
|**CTL\_E\_DIVISIONBYZERO**|0 で除算|  
|**CTL\_E\_OUTOFSTRINGSPACE**|文字列の領域を使い果たしました。|  
|**CTL\_E\_OUTOFSTACKSPACE**|スタック領域から|  
|**CTL\_E\_BADFILENAMEORNUMBER**|無効なファイル名または数|  
|**CTL\_E\_FILENOTFOUND**|ファイルが見つからない|  
|**CTL\_E\_BADFILEMODE**|不適切なファイル モード|  
|**CTL\_E\_FILEALREADYOPEN**|既に開いているファイル|  
|**CTL\_E\_DEVICEIOERROR**|デバイスの I\/O エラー|  
|**CTL\_E\_FILEALREADYEXISTS**|ファイルが既に存在している場合|  
|**CTL\_E\_BADRECORDLENGTH**|不適切なレコード長|  
|**CTL\_E\_DISKFULL**|ディスクがいっぱいです。|  
|**CTL\_E\_BADRECORDNUMBER**|不適切なレコード番号|  
|**CTL\_E\_BADFILENAME**|不適切なファイル名です|  
|**CTL\_E\_TOOMANYFILES**|ファイルの数が多すぎます|  
|**CTL\_E\_DEVICEUNAVAILABLE**|使用できないデバイス|  
|**CTL\_E\_PERMISSIONDENIED**|アクセス許可は拒否されました|  
|**CTL\_E\_DISKNOTREADY**|準備不完了ディスク|  
|**CTL\_E\_PATHFILEACCESSERROR**|パスまたはファイル アクセス エラー|  
|**CTL\_E\_PATHNOTFOUND**|パスが見つからない|  
|**CTL\_E\_INVALIDPATTERNSTRING**|無効なパターン文字列|  
|**CTL\_E\_INVALIDUSEOFNULL**|空白を使用することはできません。|  
|**CTL\_E\_INVALIDFILEFORMAT**|無効なファイル形式|  
|**CTL\_E\_INVALIDPROPERTYVALUE**|無効なプロパティ値|  
|**CTL\_E\_INVALIDPROPERTYARRAYINDEX**|無効なプロパティの配列インデックス|  
|**CTL\_E\_SETNOTSUPPORTEDATRUNTIME**|実行時にサポートされていない設定します。|  
|**CTL\_E\_SETNOTSUPPORTED**|サポートされていない設定します \(読み取り専用\) プロパティ|  
|**CTL\_E\_NEEDPROPERTYARRAYINDEX**|プロパティの配列インデックスを必要とします。|  
|**CTL\_E\_SETNOTPERMITTED**|許可されていない設定|  
|**CTL\_E\_GETNOTSUPPORTEDATRUNTIME**|実行時にサポートされていない取得します。|  
|**CTL\_E\_GETNOTSUPPORTED**|サポートされていない取得します \(書き込み専用プロパティ\)|  
|**CTL\_E\_PROPERTYNOTFOUND**|見つからないプロパティ|  
|**CTL\_E\_INVALIDCLIPBOARDFORMAT**|無効なクリップボード形式|  
|**CTL\_E\_INVALIDPICTURE**|無効なピクチャ|  
|**CTL\_E\_PRINTERERROR**|入力ミス|  
|**CTL\_E\_CANTSAVEFILETOTEMP**|TEMP にファイルを保存することはできません。|  
|**CTL\_E\_SEARCHTEXTNOTFOUND**|検索テキスト。|  
|**CTL\_E\_REPLACEMENTSTOOLONG**|置換長すぎる|  
  
 必要に応じて、標準コードの 1 つがで取り上げられていない条件のカスタム エラー コードを定義するために **CUSTOM\_CTL\_SCODE** マクロを使用します。  このマクロのパラメーターは 1000 ~ 32767 の整数。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 既存の VBX のコントロールを置き換えるために ActiveX コントロールを作成する場合は、エラー コードが互換性を確保するために VBX コントロールのと同じ数値の ActiveX コントロールのエラー コードを定義します。  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> コントロールの処理の特殊なキー  
 場合によっては特別な特定のキーストロークの組み合わせを処理したい場合があります; たとえば、ID が方向キーを押すときに Enter キーがエディット コントロールのグループ間の複数行テキスト ボックス コントロールまたは移動押すと、新しい行を挿入します。  
  
 ActiveX コントロールの基本クラスが `COleControl`場合、処理することをコンテナーの前にメッセージを処理するために [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドできます。  この方法を使用すると、`PreTranslateMessage`のオーバーライドのメッセージを処理したら **TRUE** を常に返します。  
  
 次のコード例は方向キーに関連するメッセージを処理する有効な方法を示します。  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 キーボード処理の詳細については ActiveX コントロールで、参照します ActiveX SDK ドキュメントを提供します。  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> 実行時されないアクセス ダイアログ コントロール  
 ユーザー インターフェイスを持たない、実行時されないダイアログ コントロールを作成できます。  ダイアログ ボックスに実行時の ActiveX コントロールで非表示に追加し、コントロールにアクセスするときに [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) を使用してコントロールが正しく動作しません。  代わりに、コントロールを表すオブジェクトを取得する次の 1 を使用する必要があります:  
  
-   メンバー変数の追加ウィザードを使用して、選択 **コントロール変数** は、コントロールの ID を選択します。  メンバー変数の名前を入力し、**コントロールの種類**としてコントロールのラッパー クラスを選択します。  
  
     または  
  
-   ローカル変数を宣言し、ダイアログ項目としてサブクラス化してください。  次のようなコードを挿入します。`CMyCtrl` はラッパー クラス、`IDC_MYCTRL1` です。コントロールの ID\) :  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/CPP/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)