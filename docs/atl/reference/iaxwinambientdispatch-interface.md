---
title: "IAxWinAmbientDispatch インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinAmbientDispatch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatch インターフェイス"
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAxWinAmbientDispatch インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このインターフェイスには、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
interface IAxWinAmbientDispatch : IDispatch  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[get\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::get_AllowContextMenu.md)|**AllowContextMenu** のプロパティは、ホストされているコントロールが独自のコンテキスト メニューを表示するかどうかを指定します。|  
|[get\_AllowShowUI](../Topic/IAxWinAmbientDispatch::get_AllowShowUI.md)|**AllowShowUI** のプロパティは、ホストされているコントロールが独自のユーザー インターフェイスを表示するかどうかを指定します。|  
|[get\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::get_AllowWindowlessActivation.md)|**AllowWindowlessActivation** のプロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[get\_BackColor](../Topic/IAxWinAmbientDispatch::get_BackColor.md)|`BackColor` のプロパティは、コンテナーのアンビエント背景色を指定します。|  
|[get\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::get_DisplayAsDefault.md)|**DisplayAsDefault** は、既定のコントロールでコントロールを検索するようにするアンビエント プロパティです。|  
|[get\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::get_DocHostDoubleClickFlags.md)|**DocHostDoubleClickFlags** のプロパティは、ダブルクリックに応答して発生する必要のある操作を指定します。|  
|[get\_DocHostFlags](../Topic/IAxWinAmbientDispatch::get_DocHostFlags.md)|**DocHostFlags** のプロパティは、ホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[get\_Font](../Topic/IAxWinAmbientDispatch::get_Font.md)|**\[フォント\]** のプロパティは、コンテナーのアンビエント フォントを指定します。|  
|[get\_ForeColor](../Topic/IAxWinAmbientDispatch::get_ForeColor.md)|`ForeColor` のプロパティは、コンテナーのアンビエント前景色を指定します。|  
|[get\_LocaleID](../Topic/IAxWinAmbientDispatch::get_LocaleID.md)|**LocaleID** のプロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[get\_MessageReflect](../Topic/IAxWinAmbientDispatch::get_MessageReflect.md)|**MessageReflect** のアンビエント プロパティは、コンテナーがホストされているコントロールにメッセージを返送するかどうかを指定します。|  
|[get\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::get_OptionKeyPath.md)|**OptionKeyPath** のプロパティはユーザーの設定にレジストリ キーのパスを指定します。|  
|[get\_ShowGrabHandles](../Topic/IAxWinAmbientDispatch::get_ShowGrabHandles.md)|**ShowGrabHandles** のアンビエント プロパティはグラブ ハンドルに描画するコントロールを検索するようにします。|  
|[get\_ShowHatching](../Topic/IAxWinAmbientDispatch::get_ShowHatching.md)|**ShowHatching** のアンビエント プロパティは、自身を描画するコントロールが確認できるようにします。|  
|[get\_UserMode](../Topic/IAxWinAmbientDispatch::get_UserMode.md)|**UserMode** のプロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
|[put\_AllowContextMenu](../Topic/IAxWinAmbientDispatch::put_AllowContextMenu.md)|**AllowContextMenu** のプロパティは、ホストされているコントロールが独自のコンテキスト メニューを表示するかどうかを指定します。|  
|[put\_AllowShowUI](../Topic/IAxWinAmbientDispatch::put_AllowShowUI.md)|**AllowShowUI** のプロパティは、ホストされているコントロールが独自のユーザー インターフェイスを表示するかどうかを指定します。|  
|[put\_AllowWindowlessActivation](../Topic/IAxWinAmbientDispatch::put_AllowWindowlessActivation.md)|**AllowWindowlessActivation** のプロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[put\_BackColor](../Topic/IAxWinAmbientDispatch::put_BackColor.md)|`BackColor` のプロパティは、コンテナーのアンビエント背景色を指定します。|  
|[put\_DisplayAsDefault](../Topic/IAxWinAmbientDispatch::put_DisplayAsDefault.md)|**DisplayAsDefault** は、既定のコントロールでコントロールを検索するようにするアンビエント プロパティです。|  
|[put\_DocHostDoubleClickFlags](../Topic/IAxWinAmbientDispatch::put_DocHostDoubleClickFlags.md)|**DocHostDoubleClickFlags** のプロパティは、ダブルクリックに応答して発生する必要のある操作を指定します。|  
|[put\_DocHostFlags](../Topic/IAxWinAmbientDispatch::put_DocHostFlags.md)|**DocHostFlags** のプロパティは、ホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[put\_Font](../Topic/IAxWinAmbientDispatch::put_Font.md)|**\[フォント\]** のプロパティは、コンテナーのアンビエント フォントを指定します。|  
|[put\_ForeColor](../Topic/IAxWinAmbientDispatch::put_ForeColor.md)|`ForeColor` のプロパティは、コンテナーのアンビエント前景色を指定します。|  
|[put\_LocaleID](../Topic/IAxWinAmbientDispatch::put_LocaleID.md)|**LocaleID** のプロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[put\_MessageReflect](../Topic/IAxWinAmbientDispatch::put_MessageReflect.md)|**MessageReflect** のアンビエント プロパティは、コンテナーがホストされているコントロールにメッセージを返送するかどうかを指定します。|  
|[put\_OptionKeyPath](../Topic/IAxWinAmbientDispatch::put_OptionKeyPath.md)|**OptionKeyPath** のプロパティはユーザーの設定にレジストリ キーのパスを指定します。|  
|[put\_UserMode](../Topic/IAxWinAmbientDispatch::put_UserMode.md)|**UserMode** のプロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
  
## 解説  
 このインターフェイスは、オブジェクトをホストする ATL ActiveX コントロールによって公開されます。  アンビエント プロパティは、ホストされているコントロールで使用できるように設定するか、コンテナーの動作のそのほかの側面を指定するには、このインターフェイスのメソッドを呼び出します。  プロパティを補足するには `IAxWinAmbientDispatch`を使用して [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)を提供します。  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) は、コードを含む typelib から `IAxWinAmbientDispatch` と `IAxWinAmbientDispatchEx` に関する型情報の読み込みを試みます。  
  
 ATL90.dll にリンク **AXHost** は、DLL のタイプ ライブラリから型情報を読み込みます。  
  
 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) を詳細については、" "を参照してください。  
  
## 必要条件  
 このインターフェイスの定義を次の表に示すように、複数のフォームで使用できます。  
  
|型定義|File|  
|---------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C\+\+|atliface.h \(ATLBase.h に含まれる\)|  
  
## 参照  
 [IAxWinAmbientDispatchEx インターフェイス](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow インターフェイス](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../Topic/CAxWindow::QueryHost.md)   
 [AtlAxGetHost](../Topic/AtlAxGetHost.md)