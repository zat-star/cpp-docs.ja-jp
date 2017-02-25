---
title: "CStrBufT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStrBufT<TCharType>"
  - "ATL.CStrBufT"
  - "CStrBufT"
  - "ATL::CStrBufT"
  - "ATL.CStrBufT<TCharType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStrBufT クラス"
  - "共有クラス, CStrBufT"
  - "文字列 [C++], カスタム メモリ管理"
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CStrBufT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは `GetBuffer` に自動リソースのクリーンアップを提供し、既存の `CStringT` の `ReleaseBuffer` の呼び出しを追加します。  
  
## 構文  
  
```  
  
      template<  
   typename TCharType  
>  
class CStrBufT  
```  
  
#### パラメーター  
 *TCharType*  
 `CStrBufT` のクラスの文字型。  次のいずれかになります。  
  
-   `char` \(ANSI 文字列の場合\)  
  
-   `wchar_t` \(Unicode 文字列の場合\)  
  
-   **TCHAR** \(ANSI 文字列と Unicode 文字列の両方の場合\)  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`PCXSTR`|定数文字列へのポインター。|  
|`PXSTR`|文字列へのポインター。|  
|`StringType`|The string 入力します。このバッファーがクラス テンプレートの特殊化によって処理されます。|  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CStrBufT::CStrBufT](../Topic/CStrBufT::CStrBufT.md)|文字列バッファーのオブジェクトのコンストラクター。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStrBufT::SetLength](../Topic/CStrBufT::SetLength.md)|関連付けられた文字列オブジェクトの文字バッファーの長さを設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CStrBufT::operator PCXSTR](../Topic/CStrBufT::operator%20PCXSTR.md)|関連付けられた文字列オブジェクトの文字バッファーに **const** のポインターを取得します。|  
|[CStrBufT::operator PXSTR](../Topic/CStrBufT::operator%20PXSTR.md)|関連付けられた文字列オブジェクトの文字バッファーへのポインターを取得します。|  
  
### パブリック定数  
  
|名前|説明|  
|--------|--------|  
|[CStrBufT::AUTO\_LENGTH](../Topic/CStrBufT::AUTO_LENGTH.md)|自動的にリリースで新しい文字列の長さを決定します。|  
|[CStrBufT::SET\_LENGTH](../Topic/CStrBufT::SET_LENGTH.md)|GetBuffer 時に文字列オブジェクトの長さを設定します|  
  
## 解説  
 このクラスは [GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) への呼び出しを置き換えると [ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md)ラッパー クラスとして、または [GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md) と `ReleaseBuffer`使用されます。  
  
 ヘルパー クラスとして主にデザインすると、`CStrBufT` に呼び出すか、または `ReleaseBuffer`をいつを気にせずに文字列オブジェクトの文字バッファーを使用する便利な方法を提供します。  これはラッパー オブジェクトにコード パスを終了する例外または倍数は自然に範囲の外になるためです; デストラクターを文字列リソースを解放すること。  
  
## 必要条件  
 **ヘッダー :** atlsimpstr.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)