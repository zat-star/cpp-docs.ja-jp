---
title: "フレームワーク上に構築 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- application-specific classes [MFC]
- application framework [MFC], building applications
- applications [MFC]
- MFC, application development
ms.assetid: 883f0f19-866f-4221-8a3d-5607941dc8d0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44101d4b0c9ab9bf5766514a75ef510bc5b8d7e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="building-on-the-framework"></a>フレームワークを使ったアプリケーションの作成
MFC フレームワークとアプリケーションの構成でロールは、アプリケーション固有のソース コードを指定して、どのようなメッセージと応答するコマンドを定義することで、コンポーネントを接続するにです。 クラス ライブラリで指定されているから、独自のアプリケーション固有のクラスを派生およびをオーバーライドし、基本クラスの動作を追加するには、C++ 言語と C++ の標準的な手法を使用します。  
  
 関連のトピックでは、次の表は、通常次の操作とフレームワークの役割と責任範囲の全般的な順序を説明します。  
  
-   [フレームワークとアプリケーションを構築するためのシーケンス](../mfc/sequence-of-operations-for-building-mfc-applications.md)  
  
-   [OLE アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-ole-applications.md)  
  
-   [ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)  
  
-   [データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)  
  
 ほとんどの場合、別のオプションの手順の一部が、MFC アプリケーションを作成するための手順のシーケンスとしてこれらのテーブルを追跡できます。 たとえば、ほとんどのアプリケーションは、使用できるいくつかの型からビュー クラスの 1 つの型を使用します。  
  
## <a name="see-also"></a>参照  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

