---
title: "MFC ActiveX コントロール : ActiveX コントロールのライセンス | Microsoft Docs"
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
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleObjectFactory クラス, ライセンス (コントロールの)"
  - "GetLicenseKey メソッド"
  - "ライセンス (ActiveX コントロールの)"
  - "MFC ActiveX コントロール, ライセンス"
  - "VerifyLicenseKey メソッド"
  - "VerifyUserLicense メソッド"
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX コントロール : ActiveX コントロールのライセンス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ライセンス処理、ActiveX コントロール、およびオプションの機能がユーザー コントロールを使用するか、配れる方法を制御できます。\(ライセンスの問題についての追加的な説明については、[既存の ActiveX コントロールのアップグレード](../Topic/Upgrading%20an%20Existing%20ActiveX%20Control.md)ライセンスの問題を参照してください\)。  
  
 ここでは、次のトピックについて説明します。  
  
-   [ActiveX コントロールのライセンスの概要](#_core_overview_of_activex_control_licensing)  
  
-   [ライセンス コントロールの作成](#_core_creating_a_licensed_control)  
  
-   [ライセンス処理](#_core_licensing_support)  
  
-   [ActiveX コントロールの検証のカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)  
  
 他のユーザーが ActiveX コントロールをどのように使用するかを判断するには、コントロールの開発者は、検証の割り当てを実装する ActiveX コントロールです。  購入者がコントロールを配布コントロールを使用するアプリケーションのない .LIC ファイル、できます。協定とコントロールおよび .LIC ファイルをコントロールの購入者になります。  これは、コントロールを使用するために新しいアプリケーションから最初に、からコントロールを検証せずにそのアプリケーションのユーザーを防ぎます。  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX コントロールのライセンスの概要  
 ActiveX コントロールに検証をサポートするには、[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) クラスは **IClassFactory2** インターフェイスのいくつかの関数に実装を提供し、T: **IClassFactory2::RequestLicKey**、**IClassFactory2::GetLicInfo**と **IClassFactory2::CreateInstanceLic**。  コンテナー アプリケーションの開発者がコントロールのインスタンスを作成する要求を行うと、コントロール .LIC ファイルが存在することを確認するに `GetLicInfo` への呼び出しが行われました。  コントロールが検証されると、コントロールのインスタンスがそのコンテナーに作成し、配置できます。  開発者がコンテナー アプリケーションを構築することが完了したら、関数呼び出し、`RequestLicKey`への、ここで行われます。  このコンテナー アプリケーションに関数の戻り値はライセンス キー \(単純な文字列\)。  リターン キーはアプリケーション内に埋め込まれます。  
  
 下の図に、コンテナー アプリケーションの開発時に使用する ActiveX コントロールのライセンスの検証の例を示します。  前に述べたように、コンテナー アプリケーションの開発者は、コントロールのインスタンスを作成するには、開発用コンピューターにインストールされている適切な .LIC ファイルが必要です。  
  
 ![開発時で検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d1.gif "vc374D1")  
開発時の ActiveX コントロールのライセンス検査  
  
 次の図に示します。ここでは、エンド ユーザーがコンテナー アプリケーションを実行したときに発生します。  
  
 アプリケーションの起動時には、作成される通常の各コントロールのインスタンス。  コンテナーは、パラメーターとして埋め込まれたなライセンス キーを渡す `CreateInstanceLic`を呼び出すことによってこれを実現します。  文字列比較はライセンス キーの埋め込まれたなライセンス キーとコントロールのコピー中に表示されます。  一致が成功した場合は、コントロールのインスタンスが作成され、アプリケーションは正常に実行されます。  .LIC ファイルをコントロールのユーザーのコンピューター上にある必要はないことに注意してください。  
  
 ![実行時に検証された、ライセンスされた ActiveX コントロール](../mfc/media/vc374d2.gif "vc374D2")  
実行時の ActiveX コントロールのライセンス検査  
  
 コントロールの検証は 2 種類の基本的なコンポーネントで構成されます。: コントロールを実装する特定の DLL コードとライセンスはファイル。  コードは 2 か \(または 3 個\) 関数呼び出し、および参照する文字列に、著作権表記を含む「ライセンス文字列」構成されます。  これらの呼び出しとライセンスの文字列は、コントロールの実装 \(.cpp\) ファイルにあります。  ActiveX コントロール ウィザードにより生成されたライセンス ファイルは Copyright ステートメントを持つテキスト ファイルです。  これは .LIC 拡張機能、たとえば SAMPLE.LIC プロジェクト名を使用して指定されます。  ライセンスされたコントロールは、ライセンス ファイルとともに、デザイン時の使用が必要な場合伴われなければ必要があります。  
  
##  <a name="_core_creating_a_licensed_control"></a> ライセンス コントロールの作成  
 コントロール フレームワークを作成するには、ActiveX コントロール ウィザードを使用すると、ライセンス処理を含む可能性もあります。  コントロールは、ランタイム ライセンスが必要であることを指定するときに ActiveX コントロール ウィザードはコントロール クラスに検証をサポートするコードを追加します。  コードは、関数から that Use ライセンスのキーとライセンス ファイルで構成されます。  これらの関数は、コントロールの検証をカスタマイズするために変更できます。  ライセンスのカスタマイズの詳細については、この記事の [ActiveX コントロールの検証のカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control) を後で参照します。  
  
#### コントロール プロジェクトを作成するときに ActiveX コントロール ウィザードでの検証のサポートを追加するには  
  
1.  [MFC ActiveX コントロールの作成](../mfc/reference/creating-an-mfc-activex-control.md)の手順を使用します。  ActiveX コントロール ウィザードの **\[アプリケーションの設定\]** ページはランタイム ライセンスとコントロールを作成するオプションが用意されています。  
  
 ActiveX コントロール ウィザードでは、基本的なライセンス処理を含む ActiveX コントロールのフレームワークを生成します。  検証コードの詳細については、次のトピックを参照してください。  
  
##  <a name="_core_licensing_support"></a> ライセンス処理  
 ActiveX コントロールのライセンス処理を追加するには、ActiveX コントロール ウィザードを使用すると ActiveX コントロール ウィザードは宣言する実装はコントロールのヘッダー ファイルと実装ファイルに検証機能を追加するコードを追加します。  このコードは [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) にある既定の実装をオーバーライドする `VerifyUserLicense` のメンバー関数と `GetLicenseKey` のメンバー関数で構成されます。  これらの関数は、コントロールのライセンスを取得し、検証します。  
  
> [!NOTE]
>  3 つ目のメンバー関数は、`VerifyLicenseKey` ActiveX コントロール ウィザードによって生成されていないか、ライセンス キーの検証の動作をカスタマイズするためにオーバーライドできます。  
  
 このメンバー関数は、次の操作:  
  
-   [VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)  
  
     コントロールがコントロールのライセンス ファイルの存在がシステムをチェックすることにより、デザイン時に使用できるようにすることを確認します。  この関数は **IClassFactory2::GetLicInfo** と **IClassFactory::CreateInstanceLic**処理の一部として、フレームワークによって呼び出されます。  
  
-   [GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)  
  
     コントロール DLL から一意のキーを要求します。  コンテナー アプリケーションでこのキーが埋め込まれ、`VerifyLicenseKey`とともに、コントロールのインスタンスを作成するために後で使用します。  この関数は **IClassFactory2::RequestLicKey**処理の一部として、フレームワークによって呼び出されます。  
  
-   [VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)  
  
     埋め込まれたなキー、および一意キーが同じであることを確認します。  これは、コンテナーによって使用されるようにコントロールのインスタンスを作成できるようになります。  この関数は **IClassFactory2::CreateInstanceLic** 処理の一部としてフレームワークによって呼び出され、ライセンス キーのカスタマイズされた検証を提供するためにオーバーライドできます。  既定の実装では文字列比較を実行します。  詳細については、この記事の [ActiveX コントロールの検証のカスタマイズ](#_core_customizing_the_licensing_of_an_activex_control)を、後で参照します。  
  
###  <a name="_core_header_file_modifications"></a> ヘッダー ファイルの変更  
 ActiveX コントロール ウィザードはコントロールのヘッダー ファイルに次のコードを配置します。  この例では、`CSampleCtrl` オブジェクト `factory` 2 の二つのメンバー関数は、コントロール .LIC ファイルの存在を確認するとコントロールを含むアプリケーションで使用されるライセンス キーを取得する別の宣言されます: 1  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> 実装ファイルの変更  
 ActiveX コントロール ウィザードは、コントロールの実装ファイルにライセンス ファイル名とライセンスの文字列を宣言するには、次の 2 種類のステートメントを配置する:  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  何か **szLicString** を変更すると、コントロール .LIC ファイルの最初の行を変更して検証は正しく機能しません。  
  
 ActiveX コントロール ウィザードは、コントロールの実装ファイルにコントロール クラスの `VerifyUserLicense` と `GetLicenseKey` 関数を定義するために次のコードを配置する:  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 最後に、**ActiveX Control Wizard** はコントロール プロジェクト .IDL ファイルを変更します。  **ライセンスされています** キーワードは、次の例のようにコントロールのコクラスの宣言に追加します:  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/CPP/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> ActiveX コントロールの検証のカスタマイズ  
 `VerifyUserLicense`、`GetLicenseKey`と `VerifyLicenseKey` がコントロールのクラス ファクトリの仮想メンバー関数として宣言されているため、コントロールの検証の動作をカスタマイズできます。  
  
 たとえば、コントロールに `VerifyUserLicense` または `VerifyLicenseKey` メンバー関数をオーバーライドして、検証レベルを提供できます。  この関数の中でのプロパティまたはメソッドが見つかったライセンス レベルに応じてユーザーに公開する方法を調整できます。  
  
 ユーザーに通知するためにカスタマイズされたメソッドを提供する `VerifyLicenseKey` 関数にコードを追加して作成に失敗した制御できます。  たとえば、`VerifyLicenseKey` のメンバー関数でコントロールが初期化しなかった理由ことを示すメッセージ ボックスを表示できます。  
  
> [!NOTE]
>  ActiveX コントロールのライセンスの検証をカスタマイズするに `AfxVerifyLicFile`の代わりに特定のレジストリ キーが登録情報データベースを確認します。  既定の実装の例については、このトピックの [実装ファイルの変更](#_core_implementation_file_modifications) "を参照してください。  
  
 ライセンスの追加の詳細については、[既存の ActiveX コントロールのアップグレード](../Topic/Upgrading%20an%20Existing%20ActiveX%20Control.md)ライセンスの問題を参照してください。  
  
## 参照  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)