---
title: "CStringData クラス | Microsoft Docs"
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
  - "CStringData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringData クラス"
  - "共有クラス, CStringData"
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringData クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、文字列オブジェクトのデータを表します。  
  
## 構文  
  
```  
  
struct CStringData  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[AddRef](../Topic/CStringData::AddRef.md)|文字列データ オブジェクトの参照カウントをインクリメントします。|  
|[データ](../Topic/CStringData::data.md)|文字列オブジェクトの文字データを取得します。|  
|[IsLocked](../Topic/CStringData::IsLocked.md)|関連付けられた文字列オブジェクトのバッファーがロックされているかどうかを判定します。|  
|[IsShared](../Topic/CStringData::IsShared.md)|関連付けられた文字列オブジェクトのバッファーが現在共有するかどうかを指定します。|  
|[ロック](../Topic/CStringData::Lock.md)|関連付けられた文字列オブジェクトのバッファーをロックします。|  
|[リリース](../Topic/CStringData::Release.md)|特定の文字列オブジェクトを解放します。|  
|[&#91;ロック解除&#93;](../Topic/CStringData::Unlock.md)|関連付けられた文字列オブジェクトのバッファーのロックを解除します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[nAllocLength](../Topic/CStringData::nAllocLength.md)|`XCHAR`、の割り当てられたデータの長さはなく、null で終了を含まない\)|  
|[nDataLength](../Topic/CStringData::nDataLength.md)|`XCHAR`、の現在使用したデータの長さはなく、null で終了を含まない\)|  
|[nRefs](../Topic/CStringData::nRefs.md)|オブジェクトの現在の参照カウント。|  
|[pStringMgr](../Topic/CStringData::pStringMgr.md)|この文字列オブジェクトの文字列マネージャーへのポインター。|  
  
## 解説  
 このクラスは、カスタムの文字列マネージャーを実装する開発者だけで使用しないでください。  カスタム文字列マネージャーの詳細については、[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。  
  
 このクラスは、関するさまざまな情報をカプセル化し、高い文字列に関連付けられているデータを [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、[CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、または [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) では、オブジェクトなどのオブジェクトを指定します。  すべての高い文字列オブジェクトは `CStringData` に関連付けられたオブジェクトへのポインターを格納し、同じ文字列データ オブジェクトを指すように複数の文字列オブジェクトができます。  この関係は `CStringData` のオブジェクトの参照カウント \(`nRefs`\) によって表されます。  
  
> [!NOTE]
>  特定の場合、文字列型を一つ以上 \( **CFixedString**など\) 文字列データ オブジェクトを最も高い文字列オブジェクトの共有されません。  このの詳細については、[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)を参照してください。  
  
 このデータはで構成されます:  
  
-   文字列 \([IAtlStringMgr](../Topic/IAtlStringMgr%20Class.md) 型\)のメモリ マネージャー。  
  
-   文字列の現在の長さ \([nDataLength](../Topic/CStringData::nDataLength.md)\)。  
  
-   割り当てられた文字列の長さ \([nAllocLength](../Topic/CStringData::nAllocLength.md)\)。  パフォーマンス上の理由で、これは現在の文字列の長さと異なる場合があります。  
  
-   `CStringData` のオブジェクトの現在の参照カウント \([nRefs](../Topic/CStringData::nRefs.md)\)。  この値は、文字列オブジェクトが `CStringData` の同じオブジェクトを共有しているかを判断に使用されます。  
  
-   文字列の実際の文字バッファー \([データ](../Topic/CStringData::data.md)\)。  
  
    > [!NOTE]
    >  文字列オブジェクトの実際の文字バッファーは文字列マネージャーによって割り当てられます。`CStringData` のオブジェクトに追加されます。  
  
## 必要条件  
 **ヘッダー :** atlsimpstr.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)