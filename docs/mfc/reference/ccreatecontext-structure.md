---
title: "CCreateContext 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCreateContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCreateContext 構造体"
ms.assetid: 337a0e44-d910-49a8-afc0-c7207666a9dc
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CCreateContext 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

フレームワークは `CCreateContext` 構造体を使って、ドキュメントに関連付けるフレーム ウィンドウとビューを作成します。  
  
## 構文  
  
```  
struct CCreateContext  
```  
  
## 解説  
 `CCreateContext` は構造体で、基本クラスはありません。  
  
 ウィンドウを作成すると、この構造体の値によって、ドキュメントのコンポーネントをそのデータのビューに接続するために使用する情報が指定されます。  `CCreateContext` 構造体は、作成処理を部分的にオーバーライドするとき以外は必要ありません。  
  
 `CCreateContext` 構造体の内容は、ドキュメント、フレーム ウィンドウ、ビュー、ドキュメント テンプレートのポインターです。  作成するビューのタイプを示す `CRuntimeClass` のポインターもあります。  実行時のクラスの情報と現在のドキュメントへのポインターを使って、動的に新しいビューを作成できます。  次の表に、`CCreateContext` 構造体の各メンバーがいつ、どのように使われるかを示します。  
  
|メンバー|型|用途|  
|----------|-------|--------|  
|`m_pNewViewClass`|`CRuntimeClass*`|作成する新しいビューの `CRuntimeClass`|  
|`m_pCurrentDoc`|`CDocument*`|新しいビューに関連付ける既存のドキュメント|  
|`m_pNewDocTemplate`|`CDocTemplate*`|新しい MDI フレーム ウィンドウの作成時に関連付けるドキュメント テンプレート|  
|`m_pLastView`|`CView*`|分割ウィンドウのビュー、またはドキュメントの別のビューを作成するときに、追加されるビューの原型となるビュー|  
|`m_pCurrentFrame`|`CFrameWnd*`|ドキュメントの別のフレーム ウィンドウを作成するときに、追加されるフレーム ウィンドウの原型となるフレーム ウィンドウ|  
  
 ドキュメント テンプレートによってドキュメントとその関連コンポーネントを作成すると、`CCreateContext` 構造体に格納されている情報が有効になります。  したがって、存在しないドキュメントからビューが作成されることはありません。  
  
> [!NOTE]
>  `CCreateContext` のすべてのポインターはオプションであり、指定されていない場合や未知の場合には `NULL` になります。  
  
 `CCreateContext` 構造体は、"参照" に挙げたメンバー関数で使用されます。これらの関数をオーバーライドするときの詳細については、それぞれの関数の説明を参照してください。  
  
 一般的なガイドラインは次のとおりです。  
  
-   `CWnd::Create`、`CFrameWnd::Create`、`CFrameWnd::LoadFrame` などのウィンドウ作成関数に引数として渡すと、作成コンテキストは新しいウィンドウの接続先を示します。  大部分のウィンドウでは構造体全体の指定を省略できます。この場合は、`NULL` ポインターを渡します。  
  
-   `CFrameWnd::OnCreateClient` のようなオーバライドできるメンバー関数では、`CCreateContext` 引数を省略できます。  
  
-   ビューを作成するメンバー関数に対して、ビューの作成に必要な情報を与えてください。  たとえば、分割ウィンドウの最初のビューでは、ビューのクラス情報と現在のドキュメントを与えます。  
  
 通常、既定のフレームワークを使うときは、`CCreateContext` を無視できます。  より高度な修正を行うときには、Microsoft Foundation Class ライブラリのソース コード、または、VIEWEX のようなサンプル プログラムが参考になります。  必要なパラメーターを指定し忘れると、フレームワークのアサーションによって不足パラメーターが通知されます。  
  
 `CCreateContext`の詳細については、MFC サンプル [VIEWEX](../../top/visual-cpp-samples.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** afxext.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd::Create](../Topic/CFrameWnd::Create.md)   
 [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md)   
 [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md)   
 [CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)   
 [CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)