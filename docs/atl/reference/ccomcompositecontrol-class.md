---
title: "CComCompositeControl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComCompositeControl"
  - "ATL::CComCompositeControl"
  - "ATL.CComCompositeControl<T>"
  - "ATL.CComCompositeControl"
  - "ATL::CComCompositeControl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCompositeControl クラス"
  - "複合コントロール, CComCompositeControl クラス"
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCompositeControl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、複合コントロールの実装に必要なメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T   
>  
class CComCompositeControl :  
public CComControl< T, CAxDialogImpl< T > >  
```  
  
#### パラメーター  
 `T`  
 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) か [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)から、または他のインターフェイスから派生したクラスは、複合コントロールでサポートする必要があります。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComCompositeControl::CComCompositeControl](../Topic/CComCompositeControl::CComCompositeControl.md)|コンストラクターです。|  
|[CComCompositeControl::~CComCompositeControl](../Topic/CComCompositeControl::~CComCompositeControl.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)|アドバイズするために、このメソッドまたは unadvise を複合コントロールによってホストされるすべてのコントロール呼び出します。|  
|[CComCompositeControl::CalcExtent](../Topic/CComCompositeControl::CalcExtent.md)|複合コントロールをホストするために使用されるダイアログ リソースの **HIMETRIC** 単位のサイズを計算するためにこのメソッドを呼び出します。|  
|[CComCompositeControl::Create](../Topic/CComCompositeControl::Create.md)|このメソッドは、複合コントロールのコントロール ウィンドウを作成するために呼び出されます。|  
|[CComCompositeControl::CreateControlWindow](../Topic/CComCompositeControl::CreateControlWindow.md)|コントロール ウィンドウを作成し、ホストされているコントロールに指示するには、このメソッドを呼び出します。|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](../Topic/CComCompositeControl::SetBackgroundColorFromAmbient.md)|コンテナーの背景色を使用して複合コントロールの背景色を設定するには、このメソッドを呼び出します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CComCompositeControl::m\_hbrBackground](../Topic/CComCompositeControl::m_hbrBackground.md)|背景ブラシです。|  
|[CComCompositeControl::m\_hWndFocus](../Topic/CComCompositeControl::m_hWndFocus.md)|現在フォーカスのあるウィンドウのハンドル。|  
  
## 解説  
 `CComCompositeControl` クラスから派生したクラスは、ActiveX の複合コントロールの機能を継承します。  `CComCompositeControl` から派生した ActiveX コントロールは標準のダイアログ ボックスでホストされます。  次の種類のコントロールは他のコントロールをホストするため、複合コントロールと呼ばれます \(ネイティブの Windows コントロールおよび ActiveX コントロール\)。  
  
 `CComCompositeControl` は列挙子クラスのデータ メンバーを検索することにより、複合コントロールの作成に使用するダイアログ リソースを識別します。  この子クラスのメンバー IDD は、コントロールのウィンドウとして使用されるダイアログ リソースのリソース id に設定されます。  次に `CComCompositeControl` から派生したコントロール ペインに使用するダイアログ リソースを識別するために含めるクラスが必要であるデータ メンバーの例です:  
  
 [!code-cpp[NVC_ATL_COM#13](../../atl/codesnippet/CPP/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  複合コントロールはウィンドウなしのコントロールを含めることができますが、ウィンドウ付きコントロールは、常にです。  
  
 `CComCompositeControl`で実装されたコントロールの派生クラスに組み込まれている既定の記録の動作が異なります。  含むアプリケーションにログイン コントロールはフォーカスを受け取った場合、順次 Tab キーを押すとフォーカスを複合コントロールからコンテナーのタブ オーダーで次のアイテムに複合コントロール内のコントロールすべて、循環します。  ホストされているコントロールのタブ オーダーは、ダイアログ リソースによって決定され、記録が発生する順序を決定します。  
  
> [!NOTE]
>  `CComCompositeControl`を適切に使用するアクセラレータとしてコントロールが解放されている場合、作成されるため [IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md)に再度アクセラレータ テーブルを読み込む必要が、受け渡しアクセラレータのハンドルと数を、最後にテーブルを破棄します。  
  
## 使用例  
 [!code-cpp[NVC_ATL_COM#14](../../atl/codesnippet/CPP/ccomcompositecontrol-class_2.h)]  
  
## 継承階層  
 `WinBase`  
  
 [CComControlBase](../Topic/CComControlBase%20Class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [複合コントロールの基本](../Topic/ATL%20Composite%20Control%20Fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)