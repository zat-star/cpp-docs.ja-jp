---
title: "OLE 概要: コンテナーとサーバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f8bf50dbae25390de01180f592959a7fb76a04b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ole-background-containers-and-servers"></a>OLE 概要 : コンテナーとサーバー
コンテナー アプリケーションは、独自のドキュメントに埋め込みまたはリンクされた項目を組み込むことのできるアプリケーションです。 コンテナー アプリケーションで管理されているドキュメントを保存して OLE ドキュメント コンポーネントだけでなく、アプリケーション自体によって作成されたデータを表示できる必要があります。 コンテナー アプリケーションには、ユーザーが新しい項目を挿入または既存の項目を編集するには、必要な場合に、サーバー アプリケーションをアクティブ化することも必要があります。 コンテナー アプリケーションのユーザー インターフェイスの要件は、資料に記載されて[コンテナー: ユーザー インターフェイスの問題](../mfc/containers-user-interface-issues.md)です。  
  
 サーバー アプリケーションまたはコンポーネントのアプリケーションは、コンテナー アプリケーションで使用する OLE ドキュメント コンポーネントを作成できるアプリケーションです。 通常、サーバー アプリケーションは、や、ドラッグ アンド ドロップ コンテナー アプリケーションが埋め込みまたはリンクされた項目としてデータを挿入できるように、そのデータをクリップボードにコピーをサポートします。 アプリケーションには、コンテナーとサーバーの両方を指定できます。  
  
 ほとんどのサーバーは、スタンドアロンのアプリケーションまたはフル サーバーです。これらは、スタンドアロン アプリケーションとして実行することができますか、または、コンテナー アプリケーションで起動できます。 ミニサーバーは特殊なコンテナーでのみ起動できるサーバー アプリケーションです。 それは、スタンドアロン アプリケーションとして実行することはできません。 Microsoft 描画および Graph サーバーは、miniservers の例を示します。  
  
 コンテナーとサーバーは直接通信しません。 代わりに、OLE システム ダイナミック リンク ライブラリ (DLL) を通じて通信します。 これらの Dll は、コンテナーとサーバーを呼び出す、関数を提供し、コンテナーとサーバーは、Dll が呼び出すコールバック関数を提供します。  
  
 この通信手段を使用して、サーバー アプリケーションの実装の詳細を知るコンテナーは必要ありません。 これにより、使用するサーバーの種類を定義することがなく、任意のサーバーで作成された項目をそのまま使用するためのコンテナーです。 結果として、コンテナー アプリケーションのユーザーには、将来のアプリケーションとデータ形式を活用がかかります。 これらの新しいアプリケーションが OLE コンポーネントの場合は、複合ドキュメントは、これらのアプリケーションによって作成された項目を組み込むためなります。  
  
## <a name="see-also"></a>関連項目  
 [OLE の背景知識](../mfc/ole-background.md)   
 [OLE の背景知識: MFC における実装](../mfc/ole-background-mfc-implementation.md)   
 [コンテナー](../mfc/containers.md)   
 [サーバー](../mfc/servers.md)   
 [コンテナー: クライアント アイテム](../mfc/containers-client-items.md)   
 [サーバー: サーバー アイテム](../mfc/servers-server-items.md)

