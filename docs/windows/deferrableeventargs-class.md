---
title: "DeferrableEventArgs クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DeferrableEventArgs クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

遅延のイベント引数の型に使用されるテンプレート クラス。  
  
## 構文  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### パラメーター  
 `TEventArgsInterface`  
 遅延イベントの引数を宣言するインターフェイスの型。  
  
 `TEventArgsClass`  
 `TEventArgsInterface` を実装するクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[DeferrableEventArgs::GetDeferral メソッド](../windows/deferrableeventargs-getdeferral-method.md)|遅延イベントを表す [遅延Deferral](http://go.microsoft.com/fwlink/?LinkId=526520) オブジェクトへの参照を取得します。|  
|[DeferrableEventArgs::InvokeAllFinished メソッド](../windows/deferrableeventargs-invokeallfinished-method.md)|遅延イベントを処理するすべての処理が完了したことを示すために呼び出されます。|  
  
## 解説  
 このクラスのインスタンスは、遅延イベントのイベント ハンドラーに渡されます。  テンプレート パラメーターは、遅延イベントの特定の種類のイベント引数の詳細を定義するインターフェイスと、そのインターフェイスを実装するクラスを表します。  
  
 クラスは遅延イベントのイベント ハンドラーの最初の引数として表示されます。  [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md) メソッドを呼び出して [遅延](http://go.microsoft.com/fwlink/?LinkId=526520) オブジェクトを取得し、そこから遅延イベントに関するすべての情報法を取得できます。  イベント処理を完了した後、遅延オブジェクトで Complete を呼び出す必要があります。  次に、イベント ハンドラー メソッドの終わりで、[InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) を呼び出す必要があります。これにより、すべての遅延イベントの完了が正しく伝達されます。  
  
## 必要条件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)