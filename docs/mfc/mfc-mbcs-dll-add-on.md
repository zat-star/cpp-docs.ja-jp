---
title: "MFC MBCS DLL アドオン |Microsoft ドキュメント"
ms.custom: 
ms.date: 08/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 176ed47b4d6a799cf53d2a1cea8cb232f1c2c4aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL アドオン
 **［文字セット］** プロパティを **［マルチ バイト文字セットを使用する］** または **［設定なし］**に設定している、Visual Studio 2015 の MFC プロジェクトをビルドするには、マルチバイト DLL が必要になります。  

**Visual Studio 2013**: で DLL をダウンロード[for Visual Studio 2013 のマルチバイト MFC ライブラリ](https://www.microsoft.com/en-us/download/details.aspx?id=40770)です。

**Visual Studio 2015**: DLL が Visual C セットアップ コンポーネントに含まれています。 Visual C++ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、 **［プログラミング言語］**で **［Visual C++］** と **［Microsoft Foundation Classes for C++］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C++ や MFC のインストールを促すプロンプトが表示されます。  
  
**Visual Studio 2017**: に DLL がインストールされている、 **C++ を使用したデスクトップ開発**ワークロードを選択すると**MFC および ATL サポート**から、 **のオプションのコンポーネント**ウィンドウです。

  
## <a name="see-also"></a>参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)

