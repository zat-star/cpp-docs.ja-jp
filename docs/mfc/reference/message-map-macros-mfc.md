---
title: "メッセージ マップ マクロ (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: f890e0675be58c8e20e313bea54b4145e2ce0bf3
ms.lasthandoff: 02/24/2017

---
# <a name="message-map-macros-mfc"></a>メッセージ マップ マクロ (MFC)
メッセージ マップをサポートするためには、MFC は、次のマクロを提供します。  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>メッセージ マップの宣言と定義用マクロ  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](http://msdn.microsoft.com/library/c225e7e0-a81b-495c-97f9-3e0aa1f65036)|メッセージ マップがクラスでメッセージを関数にマップ (クラス宣言で使用する必要があります) 使用されることを宣言します。|  
|[BEGIN_MESSAGE_MAP](http://msdn.microsoft.com/library/d9201e18-04e0-4639-9810-f15768627fc2)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[END_MESSAGE_MAP](http://msdn.microsoft.com/library/40f611f1-a3b4-4097-b683-091bf7cfab8b)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
  
### <a name="message-mapping-macros"></a>メッセージ割り当てマクロ  
  
|||  
|-|-|  
|[ON_COMMAND](http://msdn.microsoft.com/library/f24f8bda-2cf4-49d5-aa3d-6f2e6bb003f2)|指定したコマンドのメッセージを処理する関数を示します。|  
|[ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)|指定したコントロール通知メッセージを処理する関数を示します。|  
|[ON_MESSAGE](http://msdn.microsoft.com/library/e2faeb13-9f6e-4c0d-9f6d-b2e141a0db1e)|ユーザー定義のメッセージを処理する関数を示します。|  
|[ON_OLECMD](http://msdn.microsoft.com/library/6c86327c-3d48-42ac-9dae-e0ccd3a81793)|DocObject またはコンテナーからメニュー コマンドを処理する関数を示します。|  
|[ON_REGISTERED_MESSAGE](http://msdn.microsoft.com/library/93c1c068-ae8c-4e04-8a60-a603800ab57d)|登録済みのユーザー定義のメッセージを処理する関数を示します。|  
|[ON_REGISTERED_THREAD_MESSAGE](http://msdn.microsoft.com/library/3f598bc2-b2f0-410f-8ba0-7714502170f3)|ある場合にどの関数が登録されているユーザー定義メッセージを処理を示す、`CWinThread`クラスです。|  
|[ON_THREAD_MESSAGE](http://msdn.microsoft.com/library/f718f47a-d5b1-4514-914b-e3fe2d919003)|ある場合、どの関数がユーザー定義メッセージを処理するかを示す、`CWinThread`クラスです。|  
|[ON_UPDATE_COMMAND_UI](http://msdn.microsoft.com/library/c4de3c21-2d2e-4b89-a4ce-d0c0e2d9edc4)|指定されたユーザー インターフェイスの更新コマンド メッセージを処理する関数を示します。|  
  
### <a name="message-map-range-macros"></a>範囲指定のメッセージ マップ マクロ  
  
|||  
|-|-|  
|[割り当てるには](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0)|マクロに対する最初の&2; つのパラメーターで指定されたコマンド Id の範囲を処理する関数を示します。|  
|[ON_UPDATE_COMMAND_UI_RANGE](http://msdn.microsoft.com/library/b7105bf1-44ad-4b00-b947-31478f964729)|マクロに対する最初の&2; つのパラメーターで指定されたコマンド Id の範囲を処理する更新ハンドラーを示します。|  
|[ON_CONTROL_RANGE](http://msdn.microsoft.com/library/46f0e1bb-569b-4b8b-9b80-89701d1cd7fd)|コントロールのマクロに&2; 番目と&3; 番目のパラメーターで指定した Id の範囲からの通知を処理する関数を示します。 最初のパラメーターは、コントロールの通知メッセージをなどは**BN_CLICKED**します。|  
  
 メッセージ マップ、メッセージ マップの宣言と定義用マクロ、およびメッセージ マップ マクロの詳細については、次を参照してください。[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)と[メッセージの処理とのマッピング」](../../mfc/message-handling-and-mapping.md)します。 メッセージ マップの範囲の詳細については、次を参照してください。[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)します。  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)



