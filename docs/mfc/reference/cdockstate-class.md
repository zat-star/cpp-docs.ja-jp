---
title: "CDockState クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockState クラス"
  - "ドッキング状態"
  - "ドッキング (コントロール バー)"
  - "ドッキング (ツール ウィンドウ)"
  - "配置, コントロール バー"
  - "サイズ"
  - "サイズ, コントロール バー"
  - "状態, ドッキング可能なコントロール バー"
ms.assetid: 09e7c10b-3abd-4cb2-ad36-42420fe6bc36
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDockState クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

いくつかのドッキング コントロール バーの状態を 2 次メモリ \(ファイル\) で読み込み、アンロード、またはクリアするシリアル化された `CObject` クラスです。  
  
## 構文  
  
```  
class CDockState : public CObject  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDockState::Clear](../Topic/CDockState::Clear.md)|ドッキング状態情報をオフにします。|  
|[CDockState::GetVersion](../Topic/CDockState::GetVersion.md)|格納済みバーの状態のバージョン番号を取得します。|  
|[CDockState::LoadState](../Topic/CDockState::LoadState.md)|レジストリまたは.INI ファイルから取得のステータス情報。|  
|[CDockState::SaveState](../Topic/CDockState::SaveState.md)|レジストリまたは INI ファイルに状態情報を保存します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDockState::m\_arrBarInfo](../Topic/CDockState::m_arrBarInfo.md)|各コントロール バーの 1 エントリに格納されているドッキング状態情報へのポインターの配列。|  
  
## 解説  
 ドッキングの状態はドッキングされたかバーのサイズと位置を示します。  格納されているドッキングの状態を取得する場合、`CDockState` が表示されるまでバーの位置やチェックする、バーが現在の画面設定と表示されない場合は、を `CDockState` バーの位置をスケーリングします。  `CDockState` の主な目的は、数多くのコントロール バーの状態を保持し、その状態を保存できるようにすることで、レジストリ、アプリケーションの .INI ファイルに、またはバイナリ形式で `CArchive` のオブジェクトの内容の一部として読み込まれている。  
  
 バー、ツール バー、ステータス バー、またはダイアログ バーなどの任意のドッキング可能コントロール バーである場合もあります。  `CDockState` のオブジェクトが書き込まれ、ファイルとの間で `CArchive` のオブジェクトによって読み込みます。  
  
 [CFrameWnd::GetDockState](../Topic/CFrameWnd::GetDockState.md) は `CDockState` のオブジェクトにすべてのフレーム ウィンドウの状態情報 `CControlBar` のオブジェクトを作成し、その設定を取得します。  次 [シリアル化します。](../Topic/CObject::Serialize.md) または [CDockState::SaveState](../Topic/CDockState::SaveState.md)とストレージに `CDockState` のオブジェクトの内容を記述できます。  後でフレーム ウィンドウのコントロール バーの状態を復元する場合は、`Serialize` または [CDockState::LoadState](../Topic/CDockState::LoadState.md)の状態を読み込むことができます。フレーム ウィンドウのコントロール バーに保存した状態を追加するに [CFrameWnd::SetDockState](../Topic/CFrameWnd::SetDockState.md) を使用します。  
  
 ドッキング バー コントロールの詳細については、" " [コントロール バー](../Topic/Control%20Bars.md)、[ツール バー: ドッキングとフローティング](../../mfc/docking-and-floating-toolbars.md)と [フレーム ウィンドウ](../../mfc/frame-windows.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDockState`  
  
## 必要条件  
 **Header:** afxadv.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)