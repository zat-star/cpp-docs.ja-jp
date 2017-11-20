---
title: "FreeLibrary と AfxFreeLibrary |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- FreeLibrary
- AfxFreeLibrary
dev_langs: C++
helpviewer_keywords:
- extension DLLs [C++], unloading
- AfxFreeLibrary method
- unloading DLLs
- FreeLibrary method
- DLLs [C++], linking
- explicit linking [C++]
- DLLs [C++], unloading
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 276d93489a714dda5edd721c532c28c03b3ca41f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="freelibrary-and-afxfreelibrary"></a>FreeLibrary と AfxFreeLibrary
DLL の呼び出しに明示的にリンクされるプロセス、 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) DLL モジュールが不要になったときに機能します。 これは、モジュールの参照カウントをデクリメントに機能し、参照カウントが 0 の場合は、プロセスのアドレス空間から割り当てを解除します。  
  
 MFC アプリケーションで使用して[AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)の代わりに`FreeLibrary`MFC 拡張 DLL をアンロードします。 インターフェイス (関数プロトタイプ)`AfxFreeLibrary`と同じ`FreeLibrary`です。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL を暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [リンク方式を使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [LoadLibrary と AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>関連項目  
 [Visual C の Dll](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../mfc/reference/application-information-and-management.md#afxfreelibrary)