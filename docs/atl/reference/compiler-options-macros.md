---
title: "コンパイラ オプションに関するマクロ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コンパイラ オプション, マクロ"
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# コンパイラ オプションに関するマクロ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

これらのマクロ コントロールの特定のコンパイラの機能。  
  
|||  
|-|-|  
|[\_ATL\_ALL\_WARNINGS](../Topic/_ATL_ALL_WARNINGS.md)|以前のバージョンの ATL から変換されたプロジェクトのエラーを有効にするシンボルです。|  
|[\_ATL\_APARTMENT\_THREADED](../Topic/_ATL_APARTMENT_THREADED.md)|1 つ以上のオブジェクトでアパートメント スレッドを使用する場合に定義します。|  
|[\_ATL\_CSTRING\_EXPLICIT\_CONSTRUCTORS](../Topic/_ATL_CSTRING_EXPLICIT_CONSTRUCTORS.md)|意図しない変換を防ぐために、特定の `CString` コンストラクターを明示的に宣言します。|  
|[\_ATL\_ENABLE\_PTM\_WARNING](../Topic/_ATL_ENABLE_PTM_WARNING.md)|メンバー関数へのポインターを初期化するために、標準構文を使用する場合は C4867 コンパイラ エラーを生成する C\+\+ の標準準拠構文を使用するには、このマクロを定義します。|  
|[\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md)|1 つ以上のオブジェクトでフリー スレッドまたはニュートラル スレッドを使用する場合に定義します。|  
|[\_ATL\_MULTI\_THREADED](../Topic/_ATL_MULTI_THREADED.md)|プロジェクトが、\[両方\]、\[フリー\]、または \[ニュートラル\] としてマークされたオブジェクトを持つことを示すシンボルです。  マクロ [\_ATL\_FREE\_THREADED](../Topic/_ATL_FREE_THREADED.md) が使用されます。|  
|[\_ATL\_NO\_AUTOMATIC\_NAMESPACE](../Topic/_ATL_NO_AUTOMATIC_NAMESPACE.md)|ATL として名前空間を既定で使用できないようにするシンボルです。|  
|[\_ATL\_NO\_COM\_SUPPORT](../Topic/_ATL_NO_COM_SUPPORT.md)|COM 関連コードがプロジェクトにコンパイルされないようにするシンボルです。|  
|[ATL\_NO\_VTABLE](../Topic/ATL_NO_VTABLE.md)|vtable ポインターがクラスのコンストラクターやデストラクターで初期化されないようにするシンボルです。|  
|[ATL\_NOINLINE](../Topic/ATL_NOINLINE.md)|関数のインライン展開の禁止を示すシンボルです。|  
|[\_ATL\_SINGLE\_THREADED](../Topic/_ATL_SINGLE_THREADED.md)|、のすべてのオブジェクトがシングルスレッド モデルを使用する場合に定義します。|  
  
## 参照  
 [マクロ](../../atl/reference/atl-macros.md)