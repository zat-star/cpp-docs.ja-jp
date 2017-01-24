---
title: "C++ ウィザードの JScript 関数 | Microsoft Docs"
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
  - "ウィザード JScript メソッド"
  - "ウィザード JScript メソッド, 作成 (C++ ウィザードを)"
ms.assetid: f3046c56-cf67-4aaa-919e-8c066bfb6760
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ ウィザードの JScript 関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

|||  
|-|-|  
|[AddATLSupportToProject](../ide/addatlsupporttoproject.md)|MFC プロジェクトに ATL サポートを追加します。|  
|[AddCoclassFromFile](../Topic/AddCoclassFromFile.md)|コクラスを含むテンプレート ファイルを処理し、プロジェクトの .idl ファイルに挿入します。|  
|[AddCommonConfig](../ide/addcommonconfig.md)|既定の構成をプロジェクトに追加します。|  
|[AddFilesToProject](../Topic/AddFilesToProject.md)|Templates.inf ファイルの一覧に基づいて、すべてのファイルをプロジェクトに追加します。|  
|[AddInterfaceFromFile](../ide/addinterfacefromfile.md)|インターフェイスを含むテンプレート ファイルを処理し、プロジェクトの IDL ファイルに挿入します。|  
|[CanAddATLClass](../ide/canaddatlclass.md)|実行する予定のコード ウィザードとプロジェクトに互換性があるかどうか、つまりプロジェクトで ATL クラスを使用できるかどうかを確認するために、ウィザードによって呼び出されます。<br /><br /> PREPROCESS\_FUNCTION パラメーターが[プロジェクト コントロールの .vsz ファイル](../ide/dot-vsz-file-project-control.md)にあると、ウィザードはこの関数を呼び出して、[Visual C\+\+ Code Model](http://msdn.microsoft.com/ja-jp/dd6452c2-1054-44a1-b0eb-639a94a1216b)が使用できるかどうかを調べます。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。|  
|[CanAddClass](../ide/canaddclass.md)|PREPROCESS\_FUNCTION パラメーターがプロジェクト コントロールの .vsz ファイルにあると、ウィザードがこの関数を呼び出します。<br /><br /> この関数では、Visual C\+\+ のコード モデル オブジェクトが使用できるかどうかを確認します。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。|  
|[CanAddMFCClass](../ide/canaddmfcclass.md)|実行する予定のコード ウィザードとプロジェクトに互換性があるかどうか、つまりプロジェクトで MFC クラスを使用できるかどうかを確認するために、ウィザードによって呼び出されます。<br /><br /> PREPROCESS\_FUNCTION パラメーターがプロジェクト コントロールの .vsz ファイルにあると、ウィザードはこの関数を呼び出して、Visual C\+\+ のコード モデル オブジェクトが使用できるかどうかを調べます。  コード モデルが使用できない場合、関数はエラーをレポートし、**false** を返します。|  
|[CanAddNonAttributed](../ide/canaddnonattributed.md)|プロジェクトが属性付き ATL オブジェクトと属性なし ATL オブジェクトの両方をサポートするかどうかを指定します。|  
|[CanUseFileName](../ide/canusefilename.md)|ファイルが存在するかどうかを調べます。  ファイルが存在する場合、ウィザードはコードをマージして既存のファイルに追加するかどうかを確認するメッセージを表示します。|  
|[ConvertProjectToAttributed](../Topic/ConvertProjectToAttributed.md)|ATL プロジェクトを属性付きに変換します。|  
|[CreateInfFile](../Topic/CreateInfFile.md)|Templates.inf ファイルを作成します。|  
|[CreateProject](../ide/createproject.md)|C\+\+ プロジェクトを作成します。|  
|[CreateSafeName](../ide/createsafename.md)|C\+\+ のフレンドリ名を生成します。|  
|[DeleteFile](../ide/deletefile.md)|指定されたファイルを削除します。|  
|[DoesIncludeExist](../ide/doesincludeexist.md)|`#include` ステートメントがファイルにあるかどうかを示します。|  
|[GetCodeForDllCanUnloadNow](../Topic/GetCodeForDllCanUnloadNow.md)|DLL をアンロードするために必要なコードを取得します。|  
|[GetCodeForDllGetClassObject](../ide/getcodefordllgetclassobject.md)|DLL クラス オブジェクトのコードを取得します。|  
|[GetCodeForDllRegisterServer](../ide/getcodefordllregisterserver.md)|サーバーを登録するためのコードを取得します。|  
|[GetCodeForDllUnregisterServer](../ide/getcodefordllunregisterserver.md)|サーバーの登録を解除するためのコードを取得します。|  
|[GetCodeForExitInstance](../Topic/GetCodeForExitInstance.md)|`ExitInstance` のテキストを取得するためのヘルパー関数です。|  
|[GetCodeForInitInstance](../ide/getcodeforinitinstance.md)|[InitInstance](../Topic/CWinApp::InitInstance.md) のテキストを取得するためのヘルパー関数です。|  
|[GetExportPragmas](../Topic/GetExportPragmas.md)|関数をエクスポートするためのプラグマを取得します。|  
|[GetInterfaceClasses](../Topic/GetInterfaceClasses.md)|インターフェイスに関連付けられている `VCCodeClass` オブジェクトを返します。|  
|[GetInterfaceType](../ide/getinterfacetype.md)|インターフェイスの種類 \(カスタム、デュアル、ディスパッチ、OLE オートメーションなど\) を返します。|  
|[GetMaxID](../ide/getmaxid.md)|このインターフェイスとそのすべての基本インターフェイスのメンバーのうち、最上位の `dispid` を返します。|  
|[GetMemberfunction](../Topic/GetMemberfunction.md)|指定の名前に基づく関数オブジェクトを返します。|  
|[GetProjectFile](../Topic/GetProjectFile.md)|ファイルのプロジェクトの種類 \(.rc、.idl など\) ごとにファイル名を返します。|  
|[GetProjectPath](../ide/getprojectpath.md)|プロジェクトのディレクトリ パスを返します。|  
|[GetRuntimeErrorDesc](../ide/getruntimeerrordesc.md)|例外の種類の説明を返します。|  
|[GetUniqueFileName](../Topic/GetUniqueFileName.md)|一意のファイル名を返します。|  
|[IncludeCodeElementDeclaration](../ide/includecodeelementdeclaration.md)|`strInFile` に include ステートメントを追加します。このステートメントは、`strCodeElemName` を実装しているヘッダーをインクルードします。この処理は、そのようなヘッダーがプロジェクトで検出された場合に行われます。|  
|[InsertIntoFunction](../ide/insertintofunction.md)|`InitInstance` にコードを挿入するために `AddATLSupportToProject` で呼び出されるヘルパー関数です。|  
|[IsATLProject](../ide/isatlproject.md)|プロジェクトが ATL ベースかどうかを示します。|  
|[IsAttributedProject](../Topic/IsAttributedProject.md)|プロジェクトに属性が設定されているかどうかを示します。|  
|[IsMFCProject](../Topic/IsMFCProject.md)|プロジェクトが MFC ベースかどうかを調べます。|  
|[LineBeginsWith](../ide/linebeginswith.md)|行頭に特定の文字列があるかどうかを判別するために `InsertIntoFunction` で呼び出されるヘルパー関数です。|  
|[OffsetToLineNumber](../ide/offsettolinenumber.md)|関数本体の指定位置の行番号を調べます。|  
|[OnWizFinish](../Topic/OnWizFinish.md)|ユーザーが \[完了\] をクリックすると、ウィザードの HTML スクリプトから呼び出されます。  ウィザード コントロールの **Finish** メソッドを呼び出します。|  
|[RenderAddTemplate](../Topic/RenderAddTemplate.md)|テンプレート ファイルを処理します。オプションで、そのファイルをプロジェクトに追加できます。|  
|[SetCommonPchSettings](../ide/setcommonpchsettings.md)|プロジェクトに対してプリコンパイル済みヘッダーを設定します。|  
|[SetErrorInfo](../ide/seterrorinfo.md)|エラー情報を提供します。|  
|[SetFilters](../ide/setfilters.md)|プロジェクト フォルダーに、ソース、インクルード、リソースの各フィルターを追加します。|  
|[SetMergeProxySymbol](../ide/setmergeproxysymbol.md)|\_MERGE\_PROXYSTUB シンボルを追加するために、必要に応じてウィザードによって呼び出されます。|  
|[SetNoPchSettings](../ide/setnopchsettings.md)|プリコンパイル済みヘッダーを使用しないときに、プロジェクト構成プロパティを設定します。|  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)