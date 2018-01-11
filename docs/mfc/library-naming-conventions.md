---
title: "ライブラリの名前付け規則 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NAFXCW.LIB [MFC]
- libraries [MFC], static
- coding conventions [MFC], MFC library names
- NAFXCWD.LIB [MFC]
- console applications [MFC], MFC library versions
- naming conventions [MFC], MFC object code libraries
- object code libraries, MFC naming conventions
- object code libraries
- conventions [MFC], MFC library names
- MFC libraries, naming conventions
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14e217b3cfd9f3618046cf1a0ca825eb2e6492f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="library-naming-conventions"></a>ライブラリの名前付け規則
MFC のオブジェクト コード ライブラリは、次の名前付け規則を使用します。 ライブラリの名前、フォームがあります。  
  
 *u*AFX*c*W*d*です。LIB  
  
 小文字斜体で表示される文字がプレース ホルダーの指定子の意味は次の表に表示されます。  
  
### <a name="library-naming-conventions"></a>ライブラリの名前付け規則  
  
|指定子|値と意味|  
|---------------|-------------------------|  
|*u*|ANSI (N) または Unicode (U)|  
|*c*|作成するプログラムの種類: C = all|  
|*d*|デバッグやリリース: D = デバッグです。リリースの指定子を省略します。|  
  
 既定では、デバッグ、Intel プラットフォーム用の Windows の ANSI アプリケーションをビルドします。「NAFXCWD.Lib です。 次の表に表示されているすべてのライブラリが含まれる \atlmfc\lib ディレクトリに作成済みです。  
  
### <a name="static-link-library-naming-conventions"></a>スタティック リンク ライブラリの名前付け規則  
  
|ライブラリ|説明|  
|-------------|-----------------|  
|NAFXCW.LIB|MFC スタティック リンク ライブラリ、リリース バージョン|  
|NAFXCWD.LIB|MFC スタティック リンク ライブラリのデバッグ バージョン|  
|UAFXCW.LIB|Unicode をサポート、リリース バージョンの MFC スタティック リンク ライブラリ|  
|UAFXCWD.LIB|Unicode をサポート、デバッグ バージョンの MFC スタティック リンク ライブラリ|  
  
> [!NOTE]
>  ライブラリのバージョンをビルドする必要がある場合は、\atlmfc\src\mfc ディレクトリ内の Readme.Txt ファイルを参照してください。 このファイルは、(nmake の) で提供されたメイクファイルの使用について説明します。  
  
 詳細については、次を参照してください。 [MFC Dll の名前付け規則](../build/naming-conventions-for-mfc-dlls.md)と[Unicode バージョンの MFC ライブラリ](../mfc/unicode-in-mfc.md)です。  
  
## <a name="see-also"></a>参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

