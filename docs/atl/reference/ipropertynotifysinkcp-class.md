---
title: "IPropertyNotifySinkCP クラス | Microsoft Docs"
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
  - "IPropertyNotifySinkCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コネクション ポイント [C++], 管理"
  - "IPropertyNotifySinkCP クラス"
  - "シンク, 通知 (変更を)"
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyNotifySinkCP クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、接続可能オブジェクトのアウトゴーイング インターフェイスとして [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) のインターフェイスも公開します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      , class  
      CDV   
      = CComDynamicUnkArray >  
class IPropertyNotifySinkCP :   
public IConnectionPointImpl< T, &IID_IPropertyNotifySink, CDV>  
```  
  
#### パラメーター  
 `T`  
 `IPropertyNotifySinkCP`から派生したクラス。  
  
 `CDV`  
 コネクション ポイント シンクとの間の接続を管理するクラス。  無制限の接続を可能にする [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md)既定値はです。  接続の数を指定するか [CComUnkArray](../../atl/reference/ccomunkarray-class.md)を使用できます。  
  
## 解説  
 `IPropertyNotifySinkCP` は、基本クラス、[IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md)を使用してすべてのメソッドを継承します。  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) のインターフェイスはシンク オブジェクトがプロパティの変更に関する通知を受け取ることができます。  クラス `IPropertyNotifySinkCP` は、接続可能オブジェクトのアウトゴーイング インターフェイスとしてこのインターフェイスを公開します。  クライアントはシンク `IPropertyNotifySink` のメソッドを実装する必要があります。  
  
 `IPropertyNotifySink` のインターフェイスを表すコネクション ポイントを作成する場合に `IPropertyNotifySinkCP` からクラスを派生します。  
  
 ATL でのコネクション ポイントの使用方法の詳細については、" " [&#91;接続ポイント&#93;](../../atl/atl-connection-points.md)を参照してください。  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [IConnectionPointImpl クラス](../Topic/IConnectionPointImpl%20Class.md)   
 [IConnectionPointContainerImpl クラス](../Topic/IConnectionPointContainerImpl%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)