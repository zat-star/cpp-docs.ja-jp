---
title: "プロジェクトの作成 (ATL チュートリアル、パート 1) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
caps.latest.revision: 16
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロジェクトの作成 (ATL チュートリアル、パート 1)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、ActiveX オブジェクトを作成する属性なし ATL プロジェクトによってための一連のウォーク多角形を表示します。  オブジェクトは、ユーザーの表示を更新するには、多角形、およびコードを構成する辺の数を変更することを許可するオプションが用意されています。  
  
> [!NOTE]
>  ATL と MFC は、Visual Studio Express Edition にはサポートされていません。  
  
> [!NOTE]
>  このチュートリアルでは、POLYGON サンプルと同じソース・コードを作成します。  ソース・コードを手動で入力することを回避したい場合 [&#91;Polygon sample abstract&#93;](../top/visual-cpp-samples.md)からダウンロードできます。  このチュートリアルでは、またはを使用してそれをするように独自のプロジェクトのエラーを確認するために、多角形のソース・コードを参照。  
  
### ATL を使用して最初の ATL プロジェクトを作成するには、ウィザードを投影します  
  
1.  Visual Studio 開発環境では、**\[ファイル\]** のメニューのをクリック **\[新規作成\]** し、**プロジェクト**をクリックします。  
  
2.  **\[Visual C\+\+ プロジェクト\]** のフォルダーをクリックし、**\[ATL プロジェクト\]** を選択します。  
  
3.  プロジェクトの名前として" `[多角形]`。  
  
     ソース・コードの位置は、担当の Documents\\Visual の Studio プロジェクトに既定で表示されます、新しいフォルダーが自動的に作成されます。  
  
4.  **\[OK\]** と ATL プロジェクト ウィザードが開きますをクリックします。  
  
5.  使用できるオプションを表示します **\[アプリケーションの設定\]**。  
  
6.  作成すると同時に、コントロールは DLL として、コントロールでは、インプロセス サーバーであり **\[アプリケーションの種類\]** を保持します。  
  
7.  他のオプションを既定値のままにして、**\[完了\]** をクリックします。  
  
 ATL プロジェクト ウィザードは、複数のファイルを生成するプロジェクトを作成します。  多角形のオブジェクトを抽出して、ソリューション エクスプローラーでこれらのファイルを表示できます。  ファイルを示します。  
  
|ファイル|説明|  
|----------|--------|  
|Polygon.cpp|`DllMain`、`DllCanUnloadNow`、`DllGetClassObject`、`DllRegisterServer`と `DllUnregisterServer`の実装が含まれています。  また、プロジェクトの ATL オブジェクトのリストであるオブジェクト マップが含まれます。  これは、最初は空白です。|  
|Polygon.def|このモジュール定義ファイルは、DLL に必要なエクスポートに関する情報をリンカーに示します。|  
|Polygon.idl|、オブジェクトが特定のインターフェイスを定義するインターフェイス定義言語ファイル。|  
|Polygon.rgs|このレジストリ スクリプトは、プログラムの DLL を登録するための情報が含まれています。|  
|Polygon.rc|最初にプロジェクトの名前を含むバージョン情報と文字列を含むリソース ファイル。|  
|Resource.h|リソース ファイル用のヘッダー ファイルです。|  
|Polygonps.def|このモジュール定義ファイルは、プロキシ\/スタブ コードに必要なエクスポートに関する情報をリンカーに、アパートメント間呼び出しをサポートします。|  
|stdafx.cpp|`#include` ATL 実装ファイルです。|  
|stdafx.h|`#include` ATL ヘッダー ファイル。|  
  
1.  ソリューション エクスプローラーで、`Polygon` プロジェクトを右クリックします。  
  
2.  ショートカット メニューのをクリック **\[プロパティ\]**。  
  
3.  **\[リンカー\]** をクリックします。  **○\[Per\-User\]** に **\[リダイレクト\]** オプションを変更します。  
  
4.  **\[OK\]** をクリックします。  
  
 次の手順では、プロジェクトにコントロールを追加します。  
  
 [手順 2 ~](../atl/adding-a-control-atl-tutorial-part-2.md)  
  
## 参照  
 [チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)