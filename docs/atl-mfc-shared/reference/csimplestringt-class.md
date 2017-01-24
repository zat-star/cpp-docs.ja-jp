---
title: "CSimpleStringT クラス | Microsoft Docs"
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
  - "ATL.CSimpleStringT"
  - "ATL::CSimpleStringT"
  - "ATL::CSimpleStringT<BaseType>"
  - "ATL.CSimpleStringT<BaseType>"
  - "CSimpleStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleStringT クラス"
  - "共有クラス, CSimpleStringT"
  - "文字列 [C++], ATL クラス"
ms.assetid: 15814fcb-5b8f-4425-a97e-3b61fc9b48d8
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleStringT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`CSimpleStringT` オブジェクトを表します。  
  
## 構文  
  
```  
  
      template <typename   
      BaseType  
      >  
class CSimpleStringT  
```  
  
#### パラメーター  
 `BaseType`  
 文字列クラスの文字型。  次のいずれかの値を指定します。  
  
-   `char` \(ANSI 文字列の場合\)。  
  
-   `wchar_t` \(Unicode 文字列の場合\)。  
  
-   **TCHAR** \(ANSI 文字列と Unicode 文字列の両方の場合\)。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CSimpleStringT::PCXSTR](../Topic/CSimpleStringT::PCXSTR.md)|定数文字列へのポインター。|  
|[CSimpleStringT::PXSTR](../Topic/CSimpleStringT::PXSTR.md)|文字列へのポインター。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSimpleStringT::CSimpleStringT](../Topic/CSimpleStringT::CSimpleStringT.md)|さまざまな方法で `CSimpleStringT` オブジェクトを構築します。|  
|[CSimpleStringT::~CSimpleStringT](../Topic/CSimpleStringT::~CSimpleStringT.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleStringT::Append](../Topic/CSimpleStringT::Append.md)|`CSimpleStringT` の既存オブジェクトへの `CSimpleStringT` のオブジェクトを追加します。|  
|[CSimpleStringT::AppendChar](../Topic/CSimpleStringT::AppendChar.md)|`CSimpleStringT` の既存のオブジェクトに文字を追加します。|  
|[CSimpleStringT::CopyChars](../Topic/CSimpleStringT::CopyChars.md)|別の文字列に文字をコピーします。|  
|[CSimpleStringT::CopyCharsOverlapped](../Topic/CSimpleStringT::CopyCharsOverlapped.md)|バッファーが重複する別の文字列に文字をコピーします。|  
|[CSimpleStringT::Empty](../Topic/CSimpleStringT::Empty.md)|文字列をゼロの長さを持つように強制します。|  
|[CSimpleStringT::FreeExtra](../Topic/CSimpleStringT::FreeExtra.md)|前に文字列オブジェクトの追加によって割り当てられたメモリを解放します。|  
|[CSimpleStringT::GetAllocLength](../Topic/CSimpleStringT::GetAllocLength.md)|`CSimpleStringT` のオブジェクトに割り当てられた長さを取得します。|  
|[CSimpleStringT::GetAt](../Topic/CSimpleStringT::GetAt.md)|指定した位置にある文字を返します。|  
|[CSimpleStringT::GetBuffer](../Topic/CSimpleStringT::GetBuffer.md)|`CSimpleStringT`の文字へのポインターを返します。|  
|[CSimpleStringT::GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md)|指定の長さに省略する `CSimpleStringT`の文字へのポインターを返します。|  
|[CSimpleStringT::GetLength](../Topic/CSimpleStringT::GetLength.md)|`CSimpleStringT` のオブジェクトの文字数を返します。|  
|[CSimpleStringT::GetManager](../Topic/CSimpleStringT::GetManager.md)|`CSimpleStringT` オブジェクトのメモリ マネージャーを取得します。|  
|[CSimpleStringT::GetString](../Topic/CSimpleStringT::GetString.md)|文字列を取得します|  
|[CSimpleStringT::IsEmpty](../Topic/CSimpleStringT::IsEmpty.md)|`CSimpleStringT` のオブジェクトが文字が含まれていないかどうかをテストします。|  
|[CSimpleStringT::LockBuffer](../Topic/CSimpleStringT::LockBuffer.md)|参照カウントを無効にし、バッファーの文字列を保護します。|  
|[CSimpleStringT::Preallocate](../Topic/CSimpleStringT::Preallocate.md)|文字バッファーの固定メモリを割り当てます。|  
|[CSimpleStringT::ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)|バッファーの制御の解放は `GetBuffer`によって返される。|  
|[CSimpleStringT::ReleaseBufferSetLength](../Topic/CSimpleStringT::ReleaseBufferSetLength.md)|バッファーの制御の解放は `GetBuffer`によって返される。|  
|[CSimpleStringT::SetAt](../Topic/CSimpleStringT::SetAt.md)|指定した位置に文字を設定します。|  
|[CSimpleStringT::SetManager](../Topic/CSimpleStringT::SetManager.md)|`CSimpleStringT` オブジェクトのメモリ マネージャーを設定します。|  
|[CSimpleStringT::SetString](../Topic/CSimpleStringT::SetString.md)|`CSimpleStringT` オブジェクトの文字列を設定します。|  
|[CSimpleStringT::StringLength](../Topic/CSimpleStringT::StringLength.md)|指定された文字列の文字数を返します。|  
|[CSimpleStringT::Truncate](../Topic/CSimpleStringT::Truncate.md)|指定の長さに文字列を省略します。|  
|[CSimpleStringT::UnlockBuffer](../Topic/CSimpleStringT::UnlockBuffer.md)|参照カウントを有効にし、バッファーの文字列を解放します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CSimpleStringT::operator PCXSTR](../Topic/CSimpleStringT::operator%20PCXSTR.md)|.直接 C の式の文字列として `CSimpleStringT` のオブジェクトに格納されている文字にアクセスします。|  
|[CSimpleStringT::operator](../Topic/CSimpleStringT::operator.md)|指定した位置に文字— `GetAt`の演算子の置換を返します。|  
|[CSimpleStringT::operator \+\=](../Topic/CSimpleStringT::operator%20+=.md)|既存の文字列の末尾に新しい文字列を連結します。|  
|[CSimpleStringT::operator \=](../Topic/CSimpleStringT::operator%20=.md)|`CSimpleStringT` オブジェクトに新しい値を代入します。|  
  
## 解説  
 `CSimpleStringT` は、Visual C\+\+ でサポートされているさまざまな文字列クラスの基本クラスです。  この例では、文字列オブジェクトと基本的なバッファーの処理のメモリ管理に最小限のサポートを提供します。  高度な文字列オブジェクトの場合、[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlsimpstr.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)