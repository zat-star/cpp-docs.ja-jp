---
title: "IViewObjectExImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IViewObjectExImpl<T>"
  - "ATL.IViewObjectExImpl"
  - "ATL::IViewObjectExImpl"
  - "ATL.IViewObjectExImpl<T>"
  - "IViewObjectExImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 描画"
  - "アドバイズ シンク"
  - "IViewObjectEx ATL の実装"
  - "IViewObjectExImpl クラス"
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IViewObjectExImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは **IUnknown** を実装します。また、[IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、[IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) の各インターフェイスの既定の実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IViewObjectExImpl :  
public IViewObjectEx  
```  
  
#### パラメーター  
 `T`  
 `IViewObjectExImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IViewObjectExImpl::Draw](../Topic/IViewObjectExImpl::Draw.md)|デバイス コンテキストにコントロールに描画できます。|  
|[IViewObjectExImpl::Freeze](../Topic/IViewObjectExImpl::Freeze.md)|コントロールの描画の表示を固定したがって `Unfreeze`まで変更されません。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IViewObjectExImpl::GetAdvise](../Topic/IViewObjectExImpl::GetAdvise.md)|が 1 の場合、コントロールの既存のアドバイズ シンクの接続を取得します。|  
|[IViewObjectExImpl::GetColorSet](../Topic/IViewObjectExImpl::GetColorSet.md)|描画にコントロールで使用される論理パレットを返します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IViewObjectExImpl::GetExtent](../Topic/IViewObjectExImpl::GetExtent.md)|コントロール クラスのデータ メンバー [CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md)から HIMETRIC 単位 \(0.01 ミリメートル単位ごとの\) コントロールの表示サイズを取得します。|  
|[IViewObjectExImpl::GetNaturalExtent](../Topic/IViewObjectExImpl::GetNaturalExtent.md)|ユーザーがサイズを変更するためにコンテナーの使用にオブジェクトにサイズ変更のヒントを示します。|  
|[IViewObjectExImpl::GetRect](../Topic/IViewObjectExImpl::GetRect.md)|要求された描画の情報を示す四角形を返します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
|[IViewObjectExImpl::GetViewStatus](../Topic/IViewObjectExImpl::GetViewStatus.md)|どの描画のさまざまな側面をサポートするオブジェクトの不透明度に関する情報を返します。|  
|[IViewObjectExImpl::QueryHitPoint](../Topic/IViewObjectExImpl::QueryHitPoint.md)|指定した点が指定された四角形に存在し、`pHitResult`の [HITRESULT](http://msdn.microsoft.com/library/windows/desktop/ms682187) の値を返します。|  
|[IViewObjectExImpl::QueryHitRect](../Topic/IViewObjectExImpl::QueryHitRect.md)|コントロールを表示する四角形が指定した場所の四角形の位置を複製し、`pHitResult`の **HITRESULT** の値を返すかどうかをチェックします。|  
|[IViewObjectExImpl::SetAdvise](../Topic/IViewObjectExImpl::SetAdvise.md)|コントロールとアドバイズ シンク間の接続を設定して、シンクは、コントロール ビューの変更について通知できます。|  
|[IViewObjectExImpl::Unfreeze](../Topic/IViewObjectExImpl::Unfreeze.md)|コントロールの描画の表示を解凍します。  ATL 実装は、**E\_NOTIMPL**を返します。|  
  
## 解説  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、[IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)と [IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375) のインターフェイスは、自身を直接表示し、アドバイズ シンクを作成し、コントロールの表示の変更のコンテナーに通知するために管理するコントロールができます。  **IViewObjectEx** のインターフェイスは、ちらつきの描画などの拡張機能にコントロールの末尾がマウス クリックのコントロールについて考慮する必要があるか\) サポートを、四角形以外と透過的なコントロールとヒット テスト提供します \(たとえば。  クラス `IViewObjectExImpl` は、これらのインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
## 継承階層  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [クラスの概要](../../atl/atl-class-overview.md)