---
title: "_ATL_FUNC_INFO 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ATL_FUNC_INFO"
  - "ATL::_ATL_FUNC_INFO"
  - "ATL._ATL_FUNC_INFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_FUNC_INFO 構造体"
  - "ATL_FUNC_INFO 構造体"
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _ATL_FUNC_INFO 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ディスパッチ インターフェイスでメソッドまたはプロパティの記述に使用する型情報が含まれます。  
  
## 構文  
  
```  
  
      struct _ATL_FUNC_INFO{  
   CALLCONV cc;  
   VARTYPE vtReturn;  
   SHORT nParams;  
   VARTYPE pVarTypes[_ATL_MAX_VARTYPES];  
};  
```  
  
## メンバー  
 **cc**  
 呼び出し規約。  この構造体を [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) クラスで使用する場合は、このメンバーを **CC\_STDCALL** にする必要があります。  Windows CE では、`_ATL_FUNC_INFO` 構造体の `CALLCONV` フィールドとしてサポートされるオプションは `CC_CDECL` だけです。  その他の値はサポートされていないため、動作は定義されません。  
  
 **vtReturn**  
 関数の戻り値のバリアント型。  
  
 **nParams**  
 関数のパラメーターの数。  
  
 **pVarTypes**  
 関数のパラメーターのバリアント型の配列。  
  
## 解説  
 内部的には、ATL はこの構造体を使用してタイプ ライブラリから取得した情報を保持します。  [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) クラスおよび [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md) マクロと共に使用するイベント ハンドラーの型情報を指定する場合は、この構造体を直接操作する必要があります。  
  
## 使用例  
 IDL でディスパッチ インターフェイス メソッドが次のように定義されているとします。  
  
 [!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/CPP/atl-func-info-structure_1.idl)]  
  
 `_ATL_FUNC_INFO` 構造体を次のように定義します。  
  
 [!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/CPP/atl-func-info-structure_2.h)]  
  
## 必要条件  
 **ヘッダー:** atlcom.h  
  
## 参照  
 [構造体](../../atl/reference/atl-structures.md)   
 [IDispEventSimpleImpl クラス](../../atl/reference/idispeventsimpleimpl-class.md)   
 [SINK\_ENTRY\_INFO](../Topic/SINK_ENTRY_INFO.md)