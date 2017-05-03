---
title: "DLL (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 21
---
# DLL (C++/CX)
Visual Studio を使用して、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] アプリで利用できる、標準の Win32 DLL または [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] コンポーネント DLL のいずれかを作成できます。[!INCLUDE[vs_dev11_long](../cppcx/includes/vs-dev11-long-md.md)] より以前の Visual Studio や Visual C\+\+ コンパイラを使用して作成された標準 DLL は、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリで正しく読み込まれない場合があり、[!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)] のアプリ検証テストに合格しない場合があります。  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネント DLL  
 ほとんどの場合、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリで使用する DLL を作成するときは、その名前を持つプロジェクト テンプレートを使用して [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントとして作成してください。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の public または private 型を持つ DLL のために、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネント プロジェクトを作成できます。[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 互換の言語で記述されたアプリからアクセスできます。 既定では、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネント プロジェクトのコンパイラ設定では、**\/ZW** スイッチを使用します。 .winmd ファイルには、ルート名前空間と同じ名前が必要です。 たとえば、A.B.C.MyClass という名前のクラスは、A.winmd または A.B.winmd または A.B.C.winmd という名前のメタデータ ファイルで定義されている場合のみインスタンス化できます。 DLL の名前が .winmd ファイル名と一致する必要はありません。  
  
 詳細については、「[C\+\+ で Windows ランタイム コンポーネントを作成する](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)」を参照してください。  
  
#### プロジェクトでサードパーティの [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネント バイナリを参照するには  
  
1.  DLL を使用するプロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。**\[共通プロパティ\]** ページで、**\[新しい参照の追加\]** をクリックします。  
  
2.  [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] コンポーネントは、1 つの DLL ファイルと、メタデータを格納した 1 つの .winmd ファイルで構成されます。 通常、これらのファイルは同じフォルダーにあります。**\[参照の追加\]** ダイアログ ボックスの左ペインで、**\[参照\]** をクリックし、DLL とその .winmd ファイルの場所に移動します。 詳細については、「[チュートリアル: 拡張 SDK の作成と使用](http://msdn.microsoft.com/ja-jp/001e2fca-3d56-43ab-a5e0-0561d085679f)」を参照してください。  
  
## 標準 DLL  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] のパブリック型を利用および生成しないで、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリから利用する、C\+\+ コード用の標準 DLL を作成できます。 既存の DLL を移行して Visual Studio のこのバージョンでコンパイルするが、コードは Windows ランタイム コンポーネント プロジェクトに変換しない場合は、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL プロジェクトの種類を使用します。 次の手順を使用する場合、DLL は .appx パッケージのアプリ実行可能ファイルと一緒に配置されます。  
  
#### Visual Studio で、標準 DLL を作成するには  
  
1.  メニュー バーで、**\[ファイル\]**、**\[新規作成\]**、**\[プロジェクト\]** を選択し、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL テンプレートを選択します。  
  
2.  プロジェクトの名前を入力し、**\[OK\]** をクリックします。  
  
3.  コードを追加します。 必ず、エクスポートする対象の関数 \(`__declspec(dllexport)` など\) の `__declspec(dllexport) Add(int I, in j);` を使用してください。  
  
4.  `#include winapifamily.h` を追加して、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションの Windows SDK からのヘッダー ファイルを含め、マクロ `WINAPI_FAMILY=WINAPI_PARTITION_APP` を設定します。  
  
#### 同じソリューションから標準 DLL プロジェクトを参照するには  
  
1.  DLL を使用するプロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。**\[共通プロパティ\]** ページで、**\[新しい参照の追加\]** をクリックします。  
  
2.  左ペインで **\[ソリューション\]** をクリックし、右ペインの対応するチェック ボックスをオンにします。  
  
3.  ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。  
  
#### 標準 DLL バイナリを参照するには  
  
1.  DLL ファイル、.lib ファイル、およびヘッダー ファイルをコピーし、既知の場所 \(現在のプロジェクト フォルダーなど\) に貼り付けます。  
  
2.  DLL を使用するプロジェクトのショートカット メニューを開き、**\[プロパティ\]** をクリックします。**\[構成プロパティ\]**、**\[リンカー\]** の順にクリックし、**\[入力\]** ページで、依存関係として .lib ファイルを追加します。  
  
3.  ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。  
  
#### [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションの互換性のために既存の Win32 DLL を移行するには  
  
1.  [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL 型のプロジェクトを作成し、既存のソース コードを追加します。  
  
2.  `#include winapifamily.h` を追加して、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリケーションの Windows SDK からのヘッダー ファイルを含め、マクロ `WINAPI_FAMILY=WINAPI_PARTITION_APP` を設定します。  
  
3.  ソース コード ファイルで、必要に応じて DLL のヘッダー ファイルの `#include` ステートメントを追加します。  
  
## 参照  
 [\(NOTINBUILD\) 高度なトピック](http://msdn.microsoft.com/ja-jp/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)