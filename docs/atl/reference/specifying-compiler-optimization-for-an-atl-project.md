---
title: "ATL プロジェクトのコンパイラ最適化の指定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.optimization"
  - "vc.appwiz.ATL.vtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, コンパイラの最適化"
  - "ATL_DISABLE_NO_VTABLE マクロ"
  - "ATL_NO_VTABLE マクロ"
ms.assetid: 7f379318-66d5-43dd-a53d-530758d3a228
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ATL プロジェクトのコンパイラ最適化の指定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)は、既定では ATL\_NO\_VTABLE マクロを使用して新しいクラスを生成します。次に例を示します。  
  
```  
class ATL_NO_VTABLE CProjName  
{  
   ...  
};  
```  
  
 ATL は \_ATL\_NO\_VTABLE を以下のように定義します。  
  
```  
#ifdef _ATL_DISABLE_NO_VTABLE  
   #define ATL_NO_VTABLE  
#else  
   #define ATL_NO_VTABLE __declspec(novtable)  
#endif  
```  
  
 \_ATL\_DISABLE\_NO\_VTABLE を定義しない場合、ATL\_NO\_VTABLE マクロは `declspec(novtable)` に展開されます。  クラス宣言で `declspec(novtable)` を使用すると、クラスのコンストラクターやデストラクターで vtable ポインターが初期化されません。  プロジェクトのビルド時に、vtable および vtable が指すすべての関数はリンカーによって削除されます。  
  
 ATL\_NO\_VTABLE および `declspec(novtable)` は、直接作成できない基本クラスだけで使用します。  プロジェクトの最派生クラス \(通常は [CComObject](../../atl/reference/ccomobject-class.md)、[CComAggObject](../../atl/reference/ccomaggobject-class.md)、または [CComPolyObject](../../atl/reference/ccompolyobject-class.md)\) はプロジェクトの vtable ポインターを初期化するため、プロジェクトの最派生クラスでは `declspec(novtable)` を使用しないでください。  
  
 `declspec(novtable)` を使用するオブジェクトのコンストラクターからは、仮想関数を呼び出しません。  これらの呼び出しは、[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md) メソッドに移動してください。  
  
 `declspec(novtable)` 修飾子を使用するかどうかを判断できない場合は、クラス定義から ATL\_NO\_VTABLE マクロを削除するか、またはほかのすべての ATL ヘッダー ファイルをインクルードする前に、stdafx.h で次のように指定してマクロをグローバルに無効にできます。  
  
```  
#define _ATL_DISABLE_NO_VTABLE  
```  
  
## 参照  
 [ATL プロジェクト ウィザード](../Topic/ATL%20Project%20Wizard.md)   
 [Visual C\+\+ プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [novtable](../../cpp/novtable.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)