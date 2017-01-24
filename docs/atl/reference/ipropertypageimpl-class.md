---
title: "IPropertyPageImpl クラス | Microsoft Docs"
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
  - "IPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage ATL の実装"
  - "IPropertyPageImpl クラス"
  - "プロパティ ページ"
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyPageImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**IUnknown** を実装し、[IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) インターフェイスの既定の実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPageImpl  
```  
  
#### パラメーター  
 `T`  
 `IPropertyPageImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[IPropertyPageImpl::IPropertyPageImpl](../Topic/IPropertyPageImpl::IPropertyPageImpl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IPropertyPageImpl::Activate](../Topic/IPropertyPageImpl::Activate.md)|プロパティ ページのダイアログ ボックス ウィンドウを作成します。|  
|[IPropertyPageImpl::Apply](../Topic/IPropertyPageImpl::Apply.md)|`SetObjects`で指定された基のオブジェクトには、現在のページのプロパティの値を適用します。  ATL 実装は、`S_OK`を返します。|  
|[IPropertyPageImpl::Deactivate](../Topic/IPropertyPageImpl::Deactivate.md)|**\[ライセンス認証\]**で作成されたウィンドウを破棄します。|  
|[IPropertyPageImpl::GetPageInfo](../Topic/IPropertyPageImpl::GetPageInfo.md)|プロパティ ページについての情報を取得します。|  
|[IPropertyPageImpl::Help](../Topic/IPropertyPageImpl::Help.md)|プロパティ ページの Windows のヘルプを起動します。|  
|[IPropertyPageImpl::IsPageDirty](../Topic/IPropertyPageImpl::IsPageDirty.md)|アクティブになった時点からプロパティ ページが変更されたかどうかを示します。|  
|[IPropertyPageImpl::Move](../Topic/IPropertyPageImpl::Move.md)|位置とサイズ変更プロパティ ページ\]ダイアログ ボックス。|  
|[IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)|必要に応じて、そのままプロパティ ページの状態を変更するフラグを設定します。|  
|[IPropertyPageImpl::SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|プロパティ ページに関連付けられたオブジェクトに **IUnknown** のポインターの配列を提供します。  これらのオブジェクトは **\[適用\]**の呼び出しによって現在のページのプロパティの値を受け取ります。|  
|[IPropertyPageImpl::SetPageSite](../Topic/IPropertyPageImpl::SetPageSite.md)|プロパティ ページのプロパティ フレームと通信 `IPropertyPageSite` のポインターをプロパティ ページに示します。|  
|[IPropertyPageImpl::Show](../Topic/IPropertyPageImpl::Show.md)|プロパティ ページのダイアログ ボックスを表示するか非表示にします。|  
|[IPropertyPageImpl::TranslateAccelerator](../Topic/IPropertyPageImpl::TranslateAccelerator.md)|指定したキーストロークを処理します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[IPropertyPageImpl::m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md)|プロパティ ページの状態が変更されていないかどうかを指定します。|  
|[IPropertyPageImpl::m\_dwDocString](../Topic/IPropertyPageImpl::m_dwDocString.md)|プロパティ ページを説明する文字列が関連付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m\_dwHelpContext](../Topic/IPropertyPageImpl::m_dwHelpContext.md)|プロパティ ページに関連付けられたヘルプ トピックのコンテキストの識別子を格納します。|  
|[IPropertyPageImpl::m\_dwHelpFile](../Topic/IPropertyPageImpl::m_dwHelpFile.md)|プロパティ ページを説明するヘルプ ファイルの名前が付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m\_dwTitle](../Topic/IPropertyPageImpl::m_dwTitle.md)|プロパティ ページのタブに表示される文字列と関連付けられたリソース識別子を格納します。|  
|[IPropertyPageImpl::m\_nObjects](../Topic/IPropertyPageImpl::m_nObjects.md)|プロパティ ページに関連付けられているオブジェクトの数を格納します。|  
|[IPropertyPageImpl::m\_pPageSite](../Topic/IPropertyPageImpl::m_pPageSite.md)|プロパティ ページのプロパティ フレームと通信 `IPropertyPageSite` インターフェイスへのポインター。|  
|[IPropertyPageImpl::m\_ppUnk](../Topic/IPropertyPageImpl::m_ppUnk.md)|オブジェクトへの **IUnknown** のポインターの配列へのポインターは、プロパティ ページに関連付けられています。|  
|[IPropertyPageImpl::m\_size](../Topic/IPropertyPageImpl::m_size.md)|ピクセルでプロパティ ページのダイアログ ボックスの高さと幅が格納されます。|  
  
## 解説  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) のインターフェイスは、オブジェクトがプロパティ シート内の特定のプロパティ ページを管理できます。  クラス `IPropertyPageImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [IPropertyPage2Impl クラス](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl クラス](../Topic/IPerPropertyBrowsingImpl%20Class.md)   
 [ISpecifyPropertyPagesImpl クラス](../Topic/ISpecifyPropertyPagesImpl%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)