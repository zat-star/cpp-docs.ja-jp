---
title: "IDispEventSimpleImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispEventSimpleImpl"
  - "ATL::IDispEventSimpleImpl"
  - "ATL.IDispEventSimpleImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDispEventSimpleImpl クラス"
ms.assetid: 971d82b7-a921-47fa-a4d8-909bed377ab0
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# IDispEventSimpleImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは `IDispatch` メソッドの実装を提供しますが、タイプ ライブラリからはタイプ情報が取得されません。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
UINT nID,  
class T,  
const IID* pdiid  
>  
class ATL_NO_VTABLE IDispEventSimpleImpl :  
public _IDispEventLocator<nID, pdiid>  
```  
  
#### パラメーター  
 `nID`  
 ソース オブジェクトの一意の識別子。  `IDispEventSimpleImpl` が複合コントロールの基本クラスの場合は、必要なコンテナー内のコントロールのリソース ID を使用します。  それ以外の場合は、任意の正の整数を使用します。  
  
 `T`  
 `IDispEventSimpleImpl` から派生されるユーザーのクラス。  
  
 `pdiid`  
 このクラスで実装されるイベントのディスパッチ インターフェイスの IID へのポインター。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IDispEventSimpleImpl::Advise](../Topic/IDispEventSimpleImpl::Advise.md)|既定のイベント ソースの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|イベント ソースの接続を確立します。|  
|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|イベント ソースの接続を解除。|  
|[IDispEventSimpleImpl::GetIDsOfNames](../Topic/IDispEventSimpleImpl::GetIDsOfNames.md)|**E\_NOTIMPL**返します。|  
|[IDispEventSimpleImpl::GetTypeInfo](../Topic/IDispEventSimpleImpl::GetTypeInfo.md)|**E\_NOTIMPL**返します。|  
|[IDispEventSimpleImpl::GetTypeInfoCount](../Topic/IDispEventSimpleImpl::GetTypeInfoCount.md)|**E\_NOTIMPL**返します。|  
|[IDispEventSimpleImpl::Invoke](../Topic/IDispEventSimpleImpl::Invoke.md)|イベント ハンドラーをイベント シンク マップに示された呼び出します。|  
|[IDispEventSimpleImpl::Unadvise](../Topic/IDispEventSimpleImpl::Unadvise.md)|既定のイベント ソースの接続を解除。|  
  
## 解説  
 `IDispEventSimpleImpl` には、インターフェイスのメソッドやイベントごとに実装コードを指定する必要なくイベントのディスパッチ インターフェイスを実装する方法が用意されています。  `IDispEventSimpleImpl` は `IDispatch` メソッドの実装を提供します。  指定する必要があるのは、処理の対象となるイベントの実装だけです。  
  
 `IDispEventSimpleImpl` はクラスの[イベント シンク マップ](../Topic/BEGIN_SINK_MAP.md)と連動し、適切なハンドラー関数にイベントをルーティングします。  このクラスを使用するには、次の手順に従います。  
  
-   処理する各オブジェクトのイベントごとに、イベント シンク マップに [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md) マクロを追加します。  
  
-   各エントリのパラメーターとして [\_ATL\_FUNC\_INFO](../../atl/reference/atl-func-info-structure.md) 構造体へのポインターを渡すことによってイベントごとに型情報を指定します。  x86 プラットフォームでは、`_ATL_FUNC_INFO.cc` の値を CC\_CDECL とし、コールバック関数で \_\_stdcall のメソッドを呼び出す必要があります。  
  
-   [DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md) を呼び出して、ソース オブジェクトと基本クラス間の接続を確立します。  
  
-   接続を解除するには、[DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) を呼び出します。  
  
 イベントを処理する必要のあるオブジェクトごとに、`nID` に一意の値を指定して `IDispEventSimpleImpl` から派生させる必要があります。  あるソース オブジェクトに対するアドバイズを中止してから別のソース オブジェクトに対してアドバイズすることによって基本クラスを再利用できますが、一度に 1 つのオブジェクトで処理できるソース オブジェクトの最大数は `IDispEventSimpleImpl` 基本クラスの数によって制限されます。  
  
 **IDispEventSimplImpl** の機能は [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) と同じですが、**IDispEventSimplImpl** ではタイプ ライブラリからインターフェイスの型情報を取得しません。  ウィザードでは `IDispEventImpl` だけに基づいてコードを生成しますが、手動でコードを追加すると `IDispEventSimpleImpl` を使用できます。  イベント インターフェイスを記述するタイプ ライブラリがない場合、またはタイプ ライブラリの使用に関連するオーバーヘッドを回避する場合は、`IDispEventSimpleImpl` を使用します。  
  
> [!NOTE]
>  `IDispEventImpl` と `IDispEventSimpleImpl` には、**IUnknown::QueryInterface** の独自の実装が用意されています。この実装により、`IDispEventImpl` 基本クラスまたは `IDispEventSimpleImpl` 基本クラスは別個の COM ID として機能する一方で、メイン COM オブジェクトのクラス メンバーに直接アクセスできます。  
  
 ActiveX イベント シンクの CE ATL 実装は、HRESULT の戻り値またはイベント ハンドラーからの void のみをサポートします。その他の戻り値はサポートされていないため、動作は定義されません。  
  
 詳細については、「[IDispEventImpl のサポート](../../atl/supporting-idispeventimpl.md)」を参照してください。  
  
## 継承階層  
 `_IDispEvent`  
  
 `_IDispEventLocator`  
  
 `IDispEventSimpleImpl`  
  
## 必要条件  
 **ヘッダー :** atlcom.h  
  
## 参照  
 [\_ATL\_FUNC\_INFO 構造体](../../atl/reference/atl-func-info-structure.md)   
 [IDispatchImpl クラス](../../atl/reference/idispatchimpl-class.md)   
 [IDispEventImpl クラス](../../atl/reference/idispeventimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)   
 [クラスの概要](../../atl/atl-class-overview.md)