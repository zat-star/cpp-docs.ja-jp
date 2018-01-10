---
title: "拡張 Dll: 概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 407ed0c63dce8e350c24ac5f260876fb6ab47576
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-extension-dlls-overview"></a>MFC 拡張 Dll: 概要
MFC 拡張 DLL は、主に既存の Microsoft Foundation Class ライブラリ クラスから派生した再利用可能なクラスを実装する DLL です。 MFC 拡張 Dll は、MFC (MFC の共有バージョンとも呼ばれます) のダイナミック リンク ライブラリ バージョンを使用して構築されます。 のみ MFC の実行可能ファイル (アプリケーションまたはレギュラー MFC Dll) の MFC の共有バージョンで構築されたは、MFC 拡張 DLL を使用できます。 MFC 拡張 DLL では、MFC から新しいカスタム クラスを派生し、この拡張バージョンの MFC DLL を呼び出すアプリケーションを提供できます。  
  
 また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。 やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。 MFC を自由に渡すことができますので、MFC の共有 DLL バージョンを使用する場合、これらの関数が正しくエクスポートされる、またはアプリケーションと MFC 拡張 Dll の間で MFC の派生オブジェクトのポインター。  
  
 MFC 拡張 DLL の基本的な要件を満たしている DLL の例は、MFC のサンプルを参照してください。 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)です。 具体的には、Testdll1.cpp と Testdll2.cpp ファイルを確認します。  
  
 AFXDLL という用語は、Visual C のドキュメントでは使用されなくに注意してください。 MFC 拡張 DLL は、前者の AFXDLL と同じ特性を持ちます。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [MFC 拡張 DLL を初期化します。](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [MFC 拡張 DLL](../build/extension-dlls.md)  
  
-   [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [非 MFC DLL: 概要](../build/non-mfc-dlls-overview.md)  
  
-   [MFC と静的にリンクされている標準の MFC Dll](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされている標準の MFC Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [MFC DLL を作成します。](../mfc/reference/mfc-dll-wizard.md)  
  
## <a name="see-also"></a>参照  
 [DLL の種類](../build/kinds-of-dlls.md)