---
title: "DLL でのオートメーション |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], Automation
- Automation [C++], DLLs
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e3630aab764988ad86e6120301dfff548ad4368
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="automation-in-a-dll"></a>DLL でのオートメーション
MFC DLL ウィザードで [オートメーション] オプションを選択すると、ウィザードは、次のように。  
  
-   スターター オブジェクト記述言語 (です。ODL) ファイル  
  
-   STDAFX.h ファイル Afxole.h の include ディレクティブ  
  
-   実装、`DllGetClassObject`を呼び出した関数、 **AfxDllGetClassObject**関数  
  
-   実装、`DllCanUnloadNow`を呼び出した関数、 **AfxDllCanUnloadNow**関数  
  
-   実装、`DllRegisterServer`を呼び出した関数、[されます](../mfc/reference/coleobjectfactory-class.md#updateregistryall)関数  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [オートメーション サーバー](../mfc/automation-servers.md)  
  
## <a name="see-also"></a>参照  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)