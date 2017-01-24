---
title: "カスタム文字列マネージャーの実装 (基本的な方法) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr クラス, 使用"
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# カスタム文字列マネージャーの実装 (基本的な方法)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

文字列データのメモリ割り当て方法をカスタマイズする最も簡単な方法は、ATL 提供します。**CAtlStringMgr** のクラスが用意されています。独自のメモリ割り当てルーチンを使用することですが。  **CAtlStringMgr** のコンストラクターは一つのパラメーターを持っています: `IAtlMemMgr` オブジェクトへのポインター。  `IAtlMemMgr` はヒープにジェネリック インターフェイスを提供する抽象基本クラスです。  `IAtlMemMgr` のインターフェイスを使用すると、**CAtlStringMgr** は、文字列データの格納に使用されるメモリの割り当ておよび再割り当ておよび解放します。  いずれかの `IAtlMemMgr` 独自のインターフェイスを実装するか、5 の 1 を使用すると、メモリ マネージャーの ATL クラスを提供します。  メモリ マネージャーでラップの既存のメモリ割り当て機能を提供しました: ATL  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) ラップし、標準 CRT ヒープ関数 \([malloc](../c-runtime-library/reference/malloc.md)、[free](../c-runtime-library/reference/free.md)および\) を [realloc](../c-runtime-library/reference/realloc.md)  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md) [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)、[HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701)と [HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)を使用して Win32 ヒープのハンドルを、ラップします  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 API をラップします: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723)、[LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730)と [LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 API をラップします: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)、[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)と [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)。  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM のタスクのアロケーターの API をラップします: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)、[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)と [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 文字列のメモリ管理のために、最も便利なクラスは、複数の独立したヒープを作成できるようにするため `CWin32Heap` です。  たとえば、文字列用に別のヒープを使用する場合は、次をする可能性があります:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 プライベートの文字列マネージャーを `CString` の変数のメモリを管理するには `CString` の変数のコンストラクターにパラメーターとしてマネージャーへのポインターを渡します。:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/CPP/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## 参照  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)