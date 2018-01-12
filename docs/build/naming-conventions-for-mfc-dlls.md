---
title: "MFC Dll の名前付け規則 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC libraries [C++], naming conventions
- naming conventions [C++], MFC DLLs
- MFC DLLs [C++], naming conventions
- libraries [C++], MFC DLL names
- shared DLL versions [C++]
- DLLs [C++], naming conventions
- DLLs [C++], library names
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f7702e9babcc4769136d6deab63b627f8b09bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="naming-conventions-for-mfc-dlls"></a>MFC DLL の名前付け規則
MFC に含まれるライブラリと Dll は、構造化された名前付け規則に従います。 これにより、DLL やライブラリを使用して、目的に応じてやすくします。  
  
 アプリケーションまたはこれらの Dll を使用する MFC 拡張 Dll をビルドするためのインポート ライブラリは、DLL と同じ基本名はあるが .lib ファイル名拡張子です。  
  
### <a name="shared-dll-naming-convention"></a>共有 DLL の名前付け規則  
  
|[DLL]|説明|  
|---------|-----------------|  
|MFCx0.DLL|MFC DLL、ANSI リリース バージョン|  
|MFCx0U.DLL|MFC DLL、Unicode のリリース バージョン|  
|MFCx0D.DLL|MFC DLL、ANSI のデバッグ バージョン|  
|MFCx0UD.DLL|MFC DLL、Unicode のデバッグ バージョン|  
  
 アプリケーションや MFC 拡張 DLL からであるかどうか、MFC の共有 DLL バージョンを動的にリンクする場合、は、製品に MFCx0.DLL を含める必要があります。 アプリケーションで Unicode のサポートを必要とする場合は、代わりに MFCx0U.DLL を含めます。  
  
 MFC に DLL を静的にリンクする場合は、MFC のスタティック ライブラリのいずれかでリンクする必要があります。 これらのバージョンは、規則に従って名前は [N &#124;です。U] AFXCW [D] です。LIB。 詳細については、テーブル「スタティック リンク ライブラリの名前付け規則」を参照してください[ライブラリの名前付け規則](../mfc/library-naming-conventions.md)(MFC).  
  
 アプリケーションと共に配布可能な Visual C Dll の一覧は、Visual Studio のインストールで Redist.txt を参照してください。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [ライブラリの名前付け規則](../mfc/library-naming-conventions.md)  
  
## <a name="see-also"></a>参照  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)