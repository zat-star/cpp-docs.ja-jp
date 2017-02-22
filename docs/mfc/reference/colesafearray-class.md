---
title: "COleSafeArray クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "配列 [C++], 安全な"
  - "COleSafeArray クラス"
  - "ODBC, セーフ配列"
  - "セーフ配列"
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleSafeArray クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

任意の型および次元の配列を扱うクラスです。  
  
## 構文  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleSafeArray::COleSafeArray](../Topic/COleSafeArray::COleSafeArray.md)|`COleSafeArray` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleSafeArray::AccessData](../Topic/COleSafeArray::AccessData.md)|配列のデータへのポインターを取得します。|  
|[COleSafeArray::AllocData](../Topic/COleSafeArray::AllocData.md)|配列のメモリを割り当てます。|  
|[COleSafeArray::AllocDescriptor](../Topic/COleSafeArray::AllocDescriptor.md)|セーフ配列の記述子にメモリを割り当てます。|  
|[COleSafeArray::Attach](../Topic/COleSafeArray::Attach.md)|`COleSafeArray` のオブジェクトに **VARIANT** の既存の配列を制御できます。|  
|[COleSafeArray::Clear](../Topic/COleSafeArray::Clear.md)|基になる **VARIANT**のすべてのデータを解放します。|  
|[COleSafeArray::Copy](../Topic/COleSafeArray::Copy.md)|既存の配列のコピーが作成されます。|  
|[COleSafeArray::Create](../Topic/COleSafeArray::Create.md)|セーフ配列を作成します。|  
|[COleSafeArray::CreateOneDim](../Topic/COleSafeArray::CreateOneDim.md)|`COleSafeArray` の 1 次元オブジェクトを作成します。|  
|[COleSafeArray::Destroy](../Topic/COleSafeArray::Destroy.md)|既存の配列を破棄します。|  
|[COleSafeArray::DestroyData](../Topic/COleSafeArray::DestroyData.md)|セーフ配列のデータを破棄します。|  
|[COleSafeArray::DestroyDescriptor](../Topic/COleSafeArray::DestroyDescriptor.md)|セーフ配列の記述子を破棄します。|  
|[COleSafeArray::Detach](../Topic/COleSafeArray::Detach.md)|\(データが破棄されないように `COleSafeArray` \) のオブジェクトの **VARIANT** の配列をデタッチします。|  
|[COleSafeArray::GetByteArray](../Topic/COleSafeArray::GetByteArray.md)|[CByteArray](../../mfc/reference/cbytearray-class.md)にセーフ配列の内容をコピーします。|  
|[COleSafeArray::GetDim](../Topic/COleSafeArray::GetDim.md)|配列の次元数を返します。|  
|[COleSafeArray::GetElement](../Topic/COleSafeArray::GetElement.md)|セーフ配列の 1 つの要素を取得します。|  
|[COleSafeArray::GetElemSize](../Topic/COleSafeArray::GetElemSize.md)|サイズが、セーフ配列の要素は 1 個のサイズをバイト単位で返します。|  
|[COleSafeArray::GetLBound](../Topic/COleSafeArray::GetLBound.md)|セーフ配列の各次元の下限を返します。|  
|[COleSafeArray::GetOneDimSize](../Topic/COleSafeArray::GetOneDimSize.md)|1 次元の `COleSafeArray` オブジェクトの要素数を返します。|  
|[COleSafeArray::GetUBound](../Topic/COleSafeArray::GetUBound.md)|セーフ配列の各次元の上限を返します。|  
|[COleSafeArray::Lock](../Topic/COleSafeArray::Lock.md)|配列のロック カウントをインクリメントし、配列データへのポインターを配列の記述子に設定します。|  
|[COleSafeArray::PtrOfIndex](../Topic/COleSafeArray::PtrOfIndex.md)|インデックス付き要素へのポインターを返します。|  
|[COleSafeArray::PutElement](../Topic/COleSafeArray::PutElement.md)|配列に一つの要素を割り当てます。|  
|[COleSafeArray::Redim](../Topic/COleSafeArray::Redim.md)|セーフ配列の最下位 \(右端\) の境界を変更します。|  
|[COleSafeArray::ResizeOneDim](../Topic/COleSafeArray::ResizeOneDim.md)|1 次元の `COleSafeArray` オブジェクトの要素数を変更します。|  
|[COleSafeArray::UnaccessData](../Topic/COleSafeArray::UnaccessData.md)|配列のロック カウントをデクリメントし、`AccessData` で取得したポインターを無効にします。|  
|[COleSafeArray::Unlock](../Topic/COleSafeArray::Unlock.md)|配列のロック カウントをデクリメントします。解放またはサイズを変更できます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[COleSafeArray::operator LPCVARIANT](../Topic/COleSafeArray::operator%20LPCVARIANT.md)|`COleSafeArray` のオブジェクトの **VARIANT** の基になる構造体にアクセスします。|  
|[COleSafeArray::operator LPVARIANT](../Topic/COleSafeArray::operator%20LPVARIANT.md)|`COleSafeArray` のオブジェクトの **VARIANT** の基になる構造体にアクセスします。|  
|[COleSafeArray::operator \=](../Topic/COleSafeArray::operator%20=.md)|`COleSafeArray` のオブジェクト \(**SAFEARRAY**、**VARIANT**、`COleVariant`、または `COleSafeArray` 配列\) へのコピーの値。|  
|[COleSafeArray::operator \=\=](../Topic/COleSafeArray::operator%20==.md)|2 種類の異なる配列 \(**SAFEARRAY**、**VARIANT**、`COleVariant`、または `COleSafeArray` 配列\) を比較します。|  
|[COleSafeArray::operator \<\<](../Topic/COleSafeArray::operator%20%3C%3C.md)|ダンプ コンテキストへの `COleSafeArray` のオブジェクトの内容を出力します。|  
  
## 解説  
 `COleSafeArray`は、OLE **VARIANT** 構造体の派生クラスです。  OLE **SAFEARRAY** メンバー関数は、バイトを要素とする 1 次元配列専用の一連のメンバー関数のほか、このクラスを介して `COleSafeArray` メンバー関数を使用できます。  
  
## 継承階層  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleVariant クラス](../../mfc/reference/colevariant-class.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)