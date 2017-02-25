---
title: "CComControl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アンビエント プロパティ"
  - "CComControl クラス"
  - "CComControlBase クラス, CComControl クラス"
  - "コントロール フラグ"
  - "コントロール [ATL], コントロール ヘルパー関数"
  - "コントロール [ATL], プロパティ"
  - "ストック プロパティ, ATL"
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CComControl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ATL コントロールを作成および管理するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T,  
class WinBase= CWindowImpl< T>   
>  
class ATL_NO_VTABLE CComControl :  
public CComControlBase, public WinBase;  
```  
  
#### パラメーター  
 `T`  
 コントロールを実装するクラス。  
  
 *WinBase*  
 基本クラス、実装のウィンドウ関数。  [CWindowImpl](../Topic/CWindowImpl%20Class.md)への既定値です。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComControl::CComControl](../Topic/CComControl::CComControl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComControl::ControlQueryInterface](../Topic/CComControl::ControlQueryInterface.md)|要求されたインターフェイスへのポインターを取得します。|  
|[CComControl::CreateControlWindow](../Topic/CComControl::CreateControlWindow.md)|コントロールのウィンドウを作成します。|  
|[CComControl::FireOnChanged](../Topic/CComControl::FireOnChanged.md)|コントロールのプロパティが変更されたことをコンテナーのシンク通知します。|  
|[CComControl::FireOnRequestEdit](../Topic/CComControl::FireOnRequestEdit.md)|コンテナーが通知シンクらにコントロールのプロパティを変更しようとしていること、およびオブジェクトが移動方法であることをシンクにメッセージが表示されます。|  
|[CComControl::MessageBox](../Topic/CComControl::MessageBox.md)|メッセージ ボックスを作成、表示、および操作するには、このメソッドを呼び出します。|  
  
## 解説  
 `CComControl` は、一連の ATL コントロールのための便利なコントロールのヘルパー関数および必要なデータ メンバーです。  ATL コントロール ウィザードを使用して標準コントロールと DHTML コントロールを作成する場合、ウィザードは `CComControl`から自動的にクラスを取得します。  `CComControl` は [CComControlBase](../Topic/CComControlBase%20Class.md)のメソッドのほとんどを取得します。  
  
 コントロールの作成の詳細については、[ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)を参照してください。  ATL プロジェクト ウィザードに関する詳細については、" " [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)を参照してください。  
  
 `CComControl` のメソッドとデータ メンバーのデモについては、[CIRC](../../top/visual-cpp-samples.md) サンプルを参照してください。  
  
## 継承階層  
 `WinBase`  
  
 [CComControlBase](../Topic/CComControlBase%20Class.md)  
  
 `CComControl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CWindowImpl クラス](../Topic/CWindowImpl%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComControlBase クラス](../Topic/CComControlBase%20Class.md)   
 [CComCompositeControl クラス](../../atl/reference/ccomcompositecontrol-class.md)