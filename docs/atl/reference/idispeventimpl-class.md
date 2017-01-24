---
title: "IDispEventImpl クラス | Microsoft Docs"
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
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventImpl クラス"
ms.assetid: a64b5288-35cb-4638-aad6-2d15b1c7cf7b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDispEventImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`IDispatch` メソッドの実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid= &IID_NULL,  
const GUID* plibid= &GUID_NULL,  
WORD wMajor= 0,  
WORD wMinor= 0,  
class tihclass= CcomTypeInfoHolder  
>  
class ATL_NO_VTABLE IDispEventImpl :  
public IDispEventSimpleImpl<nID, T, pdiid>  
```  
  
#### パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。  `IDispEventImpl` が複合コントロールの基本クラスの場合は、必要なコンテナー内のコントロールのリソース ID を使用します。  それ以外の場合は、任意の正の整数を使用します。  
  
 `T`  
 `IDispEventImpl` から派生されるユーザーのクラス。  
  
 `pdiid`  
 このクラスで実装されるイベントのディスパッチ インターフェイスの IID へのポインター。  このインターフェイスは `plibid`、`wMajor`と `wMinor`によって表示されるタイプ ライブラリで定義する必要があります。  
  
 `plibid`  
 ディスパッチ インターフェイスを定義するタイプ ライブラリへのポインターが `pdiid`が指す。  **&GUID\_NULL**がオブジェクトの調達、タイプ ライブラリから読み込まれるイベント。  
  
 `wMajor`  
 タイプ ライブラリのメジャー バージョン。  既定値は 0 です。  
  
 `wMinor`  
 タイプ ライブラリのマイナー バージョン。  既定値は 0 です。  
  
 `tihclass`  
 `T` の型情報の管理に使用されるクラス。  既定値は型のクラスです `CComTypeInfoHolder`; ただし、`CComTypeInfoHolder`以外の型のクラスを使用して、このテンプレート パラメーターをオーバーライドできます。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[IDispEventImpl::\_tihclass](../../atl/reference/idispeventimpl-class.md)|型情報を管理するために使用されるクラス。  既定では、`CComTypeInfoHolder` になります。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[IDispEventImpl::IDispEventImpl](../Topic/IDispEventImpl::IDispEventImpl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IDispEventImpl::GetFuncInfoFromId](../Topic/IDispEventImpl::GetFuncInfoFromId.md)|指定したディスパッチ識別子の関数のインデックスを検索します。|  
|[IDispEventImpl::GetIDsOfNames](../Topic/IDispEventImpl::GetIDsOfNames.md)|対応する一連の DISPID 整数の引数の名前をの一つのメンバーおよびオプションのセット マップします。|  
|[IDispEventImpl::GetTypeInfo](../Topic/IDispEventImpl::GetTypeInfo.md)|オブジェクトの型情報を取得します。|  
|[IDispEventImpl::GetTypeInfoCount](../Topic/IDispEventImpl::GetTypeInfoCount.md)|型情報のインターフェイスの数を取得します。|  
|[IDispEventImpl::GetUserDefinedType](../Topic/IDispEventImpl::GetUserDefinedType.md)|ユーザー定義型の基本型を取得します。|  
  
## 解説  
 `IDispEventImpl` には、インターフェイスのメソッドやイベントごとに実装コードを指定する必要なくイベントのディスパッチ インターフェイスを実装する方法が用意されています。  `IDispEventImpl` は `IDispatch` メソッドの実装を提供します。  指定する必要があるのは、処理の対象となるイベントの実装だけです。  
  
 `IDispEventImpl` はクラスの[イベント シンク マップ](../Topic/BEGIN_SINK_MAP.md)と連動し、適切なハンドラー関数にイベントをルーティングします。  このクラスを使用するには、次の手順に従います。  
  
 、処理する各オブジェクトのイベントごとに、イベント シンク マップに [SINK\_ENTRY](../Topic/SINK_ENTRY.md) または [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md) のマクロを追加します。  `IDispEventImpl` を複合コントロールの基本クラスとして使用すると、イベント シンク マップのエントリのすべてのイベント ソースの接続を確立し、中断するに [AtlAdviseSinkMap](../Topic/AtlAdviseSinkMap.md) を呼び出すことができます。  また、またはソース オブジェクトと基本クラス間の接続を確立するより細かく制御、呼び出し [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) の場合は。  接続を解除するには、[DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) を呼び出します。  
  
 イベントを処理する必要のあるオブジェクトごとに、`nID` に一意の値を指定して `IDispEventImpl` から派生させる必要があります。  1 個のソース オブジェクトに対するアドバイズを中止してから別のソース オブジェクトに対してアドバイズする基本クラスを再利用できますが、一度に処理できるソース オブジェクトの最大数は `IDispEventImpl` の基本クラスの数によって制限されます。  
  
 `IDispEventImpl` は [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)には、[\_ATL\_FUNC\_INFO](../../atl/reference/atl-func-info-structure.md) の構造体へのポインターとして指定されたではなく、タイプ ライブラリからインターフェイスの型情報を取得する以外、同じ機能を提供します。  イベント インターフェイスを記述するタイプ ライブラリがない場合、タイプ ライブラリの使用に関連するオーバーヘッドを回避したくない場合に `IDispEventSimpleImpl` を使用します。  
  
> [!NOTE]
>  が、メイン COM オブジェクト クラス メンバーへの直接アクセスを許可しながら`IDispEventImpl` と `IDispEventSimpleImpl` は **IUnknown::QueryInterface** の独自の実装を提供します。他の COM ID として機能する `IDispEventImpl` と `IDispEventSimpleImpl` の各基本クラスを有効にします。  
  
 ActiveX イベント シンクの CE ATL 実装は、HRESULT の戻り値またはイベント ハンドラーからの void のみをサポートします。その他の戻り値はサポートされていないため、動作は定義されません。  
  
 詳細については、「[IDispEventImpl のサポート](../../atl/supporting-idispeventimpl.md)」を参照してください。  
  
## 継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md)  
  
 `IDispEventImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [\_ATL\_FUNC\_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventSimpleImpl クラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY](../Topic/SINK_ENTRY.md)   
 [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY_EX.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [クラスの概要](../../atl/atl-class-overview.md)