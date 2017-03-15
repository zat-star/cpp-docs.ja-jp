---
title: "ATL のイベント処理の概要 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "イベント処理, 実装"
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL のイベント処理の概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

一般に、COM イベントを処理するのは比較的簡単です。  3 種類の主要な手順があります:  
  
-   では、オブジェクトのイベント インターフェイスを実装します。  
  
-   、オブジェクトがイベントを受信するイベント ソースに指示します。  
  
-   、のオブジェクトが、イベントを受信する必要がない場合に Unadvise イベント ソース。  
  
## インターフェイスの実装  
 ATL を使用してインターフェイスを実装する 4 主に二つの方法があります。  
  
|から派生させる。|インターフェイスの種類に適した|すべての methods\* を実装する必要があります。|実行時にタイプ ライブラリが必要です|  
|--------------|---------------------|----------------------------------|------------------------|  
|インターフェイス|Vtable|はい|いいえ|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Dual|はい|はい|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|ディスパッチ インターフェイス|いいえ|はい|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|ディスパッチ インターフェイス|いいえ|いいえ|  
  
 \* ATL のサポート クラスを使用すると、は **IUnknown** または `IDispatch` のメソッドを手動で実装する必要はありません。  
  
## アドバイズ イベント ソースと Unadvising  
 ATL を使用してイベント ソースに指示すると unadvising 3 主に二つの方法があります。  
  
|関数に指示します。|Unadvise 関数|使用するように最も適した|クッキーを追跡するために必要ですか。|コメント|  
|---------------|-----------------|------------------|------------------------|----------|  
|[AtlAdvise](../Topic/AtlAdvise.md)、[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|[AtlUnadvise](../Topic/AtlUnadvise.md)|Vtable またはデュアル インターフェイス|はい|`AtlAdvise` は、グローバル ATL 関数です。  `CComPtrBase::Advise` は [CComPtr](../atl/reference/ccomptr-class.md) と [CComQIPtr](../atl/reference/ccomqiptr-class.md)によって使用されます。|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) か [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|いいえ|基本クラスは、より多くの作業を行うため `AtlAdvise` ほどのパラメーター。|  
|[CComCompositeControl::AdviseSinkMap \(true\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|[CComCompositeControl::AdviseSinkMap \(False\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|複合コントロールの ActiveX コントロール|いいえ|`CComCompositeControl::AdviseSinkMap` は、イベント シンク マップのすべてのエントリに指示されます。  同じ関数のエントリ unadvises。  このメソッドは `CComCompositeControl` のクラスによって自動的に呼び出されます。|  
|[CAxDialogImpl::AdviseSinkMap \(true\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|[CAxDialogImpl::AdviseSinkMap \(False\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|ダイアログ ボックスの ActiveX コントロール|いいえ|`CAxDialogImpl::AdviseSinkMap` は unadvises ダイアログ リソースのすべての ActiveX コントロールをお勧めします。  この設定は自動的に行われます。|  
  
## 参照  
 [イベント処理](../Topic/Event%20Handling%20and%20ATL.md)   
 [IDispEventImpl のサポート](../atl/supporting-idispeventimpl.md)