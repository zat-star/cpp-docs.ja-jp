---
title: "メッセージ マップの参照先 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, message map
- locating message maps
- message classes [MFC], finding
- message-map macros
ms.assetid: bf59fbc8-b222-42d3-b5d3-0a79aa3cb923
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6fa0b0b31d76c55851d69f4c528f11e7d23ff0d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-find-message-maps"></a>メッセージ マップの所在
アプリケーション ウィザードを使用して新しいスケルトン アプリケーションを作成するときにアプリケーションのウィザードの作成コマンド ターゲット クラスごとのメッセージ マップを書き込みます。 これには、派生したアプリケーション、ドキュメント、ビュー、およびフレーム ウィンドウ クラスが含まれます。 メッセージの特定と定義済みのコマンドでは、アプリケーションのウィザードで指定されたエントリが既にあるこれらのメッセージ マップの一部と、単なるプレース ホルダーを追加するハンドラーの一部はします。  
  
 クラスのメッセージ マップは、します。クラスの CPP ファイルです。 メッセージと各クラスを処理するコマンドのエントリを追加するのに [プロパティ] ウィンドウを使用するアプリケーションのウィザードを作成する基本的なメッセージ マップを使用します。 いくつかのエントリを追加した後、通常のメッセージ マップは、次のようになります。  
  
 [!code-cpp[NVC_MFCMessageHandling#1](../mfc/codesnippet/cpp/where-to-find-message-maps_1.cpp)]  
  
 メッセージ マップは、マクロのコレクションで構成されます。 2 つのマクロ[BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map)と[END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map)、メッセージ マップを角かっこです。 その他のマクロなど`ON_COMMAND`、メッセージ マップの内容を入力します。  
  
> [!NOTE]
>  セミコロンでは、メッセージ マップ マクロは追跡されません。  
  
 新しいクラスを作成するクラスの追加ウィザードを使用する場合は、クラスのメッセージ マップを提供します。 また、ソース コード エディターを使用して手動でメッセージ マップを作成できます。  
  
## <a name="see-also"></a>参照  
 [フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)

