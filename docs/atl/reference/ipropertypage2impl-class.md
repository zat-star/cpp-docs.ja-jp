---
title: "IPropertyPage2Impl クラス | Microsoft Docs"
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
  - "IPropertyPage2Impl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage2 ATL の実装"
  - "IPropertyPage2Impl クラス"
  - "プロパティ ページ"
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPage2Impl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**IUnknown** を実装し、[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) の既定の実装を継承します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPage2Impl : public IPropertyPageImpl< T>  
```  
  
#### パラメーター  
 `T`  
 `IPropertyPage2Impl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPropertyPage2Impl::EditProperty](../Topic/IPropertyPage2Impl::EditProperty.md)|プロパティ ページがアクティブになったときにどのプロパティのコントロールがフォーカスを受け取るかを指定します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
  
## 解説  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) のインターフェイスは `EditProperty` のメソッドを追加することによって [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) を拡張します。  このメソッドは、クライアントがプロパティ ページ オブジェクトの特定のプロパティを選択できるようにします。  
  
 クラス `IPropertyPage2Impl` は **IPropertyPage2::EditProperty**の **E\_NOTIMPL** を返します。  ただし、[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) の既定の実装を継承し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 プロパティ ページを作成すると、クラスは通常 `IPropertyPageImpl`から派生します。  **IPropertyPage2**の追加サポートを提供するには、クラス定義を変更して、`EditProperty` のメソッドをオーバーライドします。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [IPerPropertyBrowsingImpl クラス](../Topic/IPerPropertyBrowsingImpl%20Class.md)   
 [ISpecifyPropertyPagesImpl クラス](../Topic/ISpecifyPropertyPagesImpl%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)