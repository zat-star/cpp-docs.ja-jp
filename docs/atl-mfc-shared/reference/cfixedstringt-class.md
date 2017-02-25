---
title: "CFixedStringT クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFixedStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT クラス"
  - "共有クラス, CFixedStringT"
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CFixedStringT クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、固定文字バッファーによって文字列オブジェクトを表します。  
  
## 構文  
  
```  
  
      template< class   
      StringType  
      , int   
      t_nChars  
       >    
class CFixedStringT : private CFixedStringMgr, public StringType  
```  
  
#### パラメーター  
 `StringType`  
 ように基本クラスが固定文字列オブジェクトで使用されて `CStringT`のどのベースの型です。  たとえば、`CString`、`CStringA`と `CStringW`が含まれます。  
  
 *t\_nChars*  
 バッファーに格納された文字数。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFixedStringT::CFixedStringT](../Topic/CFixedStringT::CFixedStringT.md)|文字列オブジェクトのコンストラクター。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CFixedStringT::operator \=](../Topic/CFixedStringT::operator%20=.md)|`CFixedStringT` オブジェクトに新しい値を代入します。|  
  
## 解説  
 このクラスは `CStringT`に基づいてカスタム文字列クラスの例です。  非常に似ていますが、2 種類のクラスは実装によって異なります。  `CFixedStringT` と `CStringT` との主な相違点は次のとおりです:  
  
-   最初の文字バッファーは、オブジェクトの一部として割り当てられているサイズの *t\_nChars*があります。  これは **CFixedString** のオブジェクトがパフォーマンスの向上のために、連続メモリのチャンクを割り当てることにします。  ただし、`CFixedStringT` のオブジェクトの内容が *t\_nChars*を超えて育てば、バッファーは動的に割り当てられます。  
  
-   `CFixedStringT` のオブジェクトの文字バッファーは同じ長さ \(*t\_nChars*\) 常にです。  `CStringT` のオブジェクトのバッファー サイズに制限はありません。  
  
-   `CFixedStringT` のメモリ マネージャーは複数の [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 間でオブジェクトを共有できません `CFixedStringT` の objectsis ようにカスタマイズします。  `CStringT` のオブジェクトにこの制限はありません。  
  
 `CFixedStringT` のカスタマイズと、一般に文字列オブジェクトのメモリ管理の詳細については、[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。  
  
## 継承階層  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## 必要条件  
 **ヘッダー:** cstringt.h  
  
## 参照  
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)