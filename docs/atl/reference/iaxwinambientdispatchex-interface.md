---
title: "IAxWinAmbientDispatchEx インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IAxWinAmbientDispatchEx"
  - "IAxWinAmbientDispatchEx"
  - "ATL::IAxWinAmbientDispatchEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinAmbientDispatchEx インターフェイス"
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# IAxWinAmbientDispatchEx インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このインターフェイスは、ホストされるコントロールを補足するアンビエント プロパティを実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      MIDL_INTERFACE( "B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5" )  
IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[SetAmbientDispatch](../Topic/IAxWinAmbientDispatchEx::SetAmbientDispatch.md)|このメソッドは、ユーザー定義のインターフェイスに対して既定のアンビエント プロパティのインターフェイスを補足するために呼び出されます。|  
  
## 解説  
 ATL に静的にリンクする場合は、ActiveX コントロールをホストする ATL アプリケーション、アンビエント プロパティを持つ ActiveX コントロールに特にこのインターフェイスを含めます。  このインターフェイスが、このアサーションを生成します: 「CComModule::Init に LIBID を渡すことをお勧めします」。  
  
 このインターフェイスは、オブジェクトをホストする ATL ActiveX コントロールによって公開されます。  [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)から派生した、`IAxWinAmbientDispatchEx` は、ATL によって提供される独自の 1 のアンビエント プロパティのインターフェイスを補うことができるメソッドを追加します。  
  
 [AXHost](https://msdn.microsoft.com/en-us/library/system.windows.forms.axhost.aspx) は、コードを含むタイプ ライブラリの `IAxWinAmbientDispatch` と `IAxWinAmbientDispatchEx` に関する型情報の読み込みを試みます。  
  
 ATL90.dll にリンク **AXHost** は、DLL のタイプ ライブラリから型情報を読み込みます。  
  
 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) を詳細については、" "を参照してください。  
  
## 必要条件  
 このインターフェイスの定義を次の表に示すように、複数のフォームで使用できます。  
  
|型定義|ファイル|  
|---------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C\+\+|atliface.h \(ATLBase.h に含まれる\)|  
  
## 参照  
 [IAxWinAmbientDispatch インターフェイス](../../atl/reference/iaxwinambientdispatch-interface.md)