---
title: "CComVariant クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComVariant"
  - "ATL::CComVariant"
  - "CComVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComVariant クラス"
  - "VARIANT マクロ"
  - "VARIANT マクロ, ATL"
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComVariant クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは `VARIANT` 型をラップし、格納されたデータの型を示すメンバーを提供します。  
  
## 構文  
  
```  
  
class CComVariant : public tagVARIANT  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComVariant::CComVariant](../Topic/CComVariant::CComVariant.md)|コンストラクターです。|  
|[CComVariant::~CComVariant](../Topic/CComVariant::~CComVariant.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComVariant::Attach](../Topic/CComVariant::Attach.md)|`CComVariant` のオブジェクトに **VARIANT** をアタッチします。|  
|[CComVariant::ChangeType](../Topic/CComVariant::ChangeType.md)|`CComVariant` オブジェクトを新しい型に変換します。|  
|[CComVariant::Clear](../Topic/CComVariant::Clear.md)|`CComVariant` のオブジェクトをクリアします。|  
|[CComVariant::Copy](../Topic/CComVariant::Copy.md)|`CComVariant` のオブジェクトに **VARIANT** をコピーします。|  
|[CComVariant::CopyTo](../Topic/CComVariant::CopyTo.md)|`CComVariant` のオブジェクトの内容をコピーします。|  
|[CComVariant::Detach](../Topic/CComVariant::Detach.md)|`CComVariant` のオブジェクトの基になる **VARIANT** をデタッチします。|  
|[CComVariant::GetSize](../Topic/CComVariant::GetSize.md)|`CComVariant` のオブジェクトの内容のサイズのバイト数を返します。|  
|[CComVariant::ReadFromStream](../Topic/CComVariant::ReadFromStream.md)|ストリームからの **VARIANT** を読み込みます。|  
|[CComVariant::SetByRef](../Topic/CComVariant::SetByRef.md)|`CComVariant` のオブジェクトを初期化し、**VT\_BYREF**に **vt** のメンバーを設定します。|  
|[CComVariant::WriteToStream](../Topic/CComVariant::WriteToStream.md)|基になるストリームに **VARIANT** を保存します。|  
  
### パブリック演算子  
  
|||  
|-|-|  
|[CComVariant::operator \<](../Topic/CComVariant::operator%20%3C.md)|`CComVariant` のオブジェクトが、指定 **VARIANT**より小さいかどうかを示します。|  
|[CComVariant::operator \>](../Topic/CComVariant::operator%20%3E.md)|`CComVariant` のオブジェクトが、指定 **VARIANT**より大きいかどうかを示します。|  
|[operator \!\=](../Topic/CComVariant::operator%20!=.md)|`CComVariant` のオブジェクトが、指定しない **VARIANT**に等しいかどうかを示します。|  
|[operator \=](../Topic/CComVariant::operator%20=.md)|`CComVariant` オブジェクトに値を割り当てます。|  
|[operator \=\=](../Topic/CComVariant::operator%20==.md)|`CComVariant` オブジェクトが、指定された **VARIANT** と等しいかどうかを示します。|  
  
## 解説  
 `CComVariant` は、`VARIANT and VARIANTARG` 型をラップします。この型は、共用体とその共用体に格納されたデータの型を示すメンバーで構成されます。  **VARIANT** 型は、通常、オートメーションで使われます。  
  
 `CComVariant` は **VARIANT** 型から派生しているため、**VARIANT** を使用できる箇所では常に使用できます。  たとえば、**V\_VT** マクロを使用して `CComVariant` の型を抽出できます。また、**VARIANT** の場合と同様に **vt** メンバーに直接アクセスできます。  
  
## 継承階層  
 `tagVARIANT`  
  
 `CComVariant`  
  
## 必要条件  
 ヘッダー : atlcomcli.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)