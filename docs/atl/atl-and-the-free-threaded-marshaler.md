---
title: "ATL とフリー スレッド マーシャラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02b8586d7df5a521b48bfce61a097ed6ca450196
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL とフリー スレッド マーシャラー
ATL シンプル オブジェクト ウィザードの [属性] ページでは、フリー スレッド マーシャラー (FTM) を集計するクラスを許可するオプションを提供します。  
  
 ウィザードでのフリー スレッド マーシャラーのインスタンスを作成するコードを生成`FinalConstruct`でそのインスタンスを解放し、`FinalRelease`です。 A`COM_INTERFACE_ENTRY_AGGREGATE`マクロは自動的にいることを確認する COM マップに追加`QueryInterface`に対する要求[IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)フリー スレッド マーシャラーによって処理されます。  
  
 フリー スレッド マーシャラーに直接アクセスできるオブジェクトのインターフェイス、同じプロセス内の任意のスレッドからアパートメント間の呼び出しを高速化します。 このオプションは、両方、スレッディング モデルを使用するクラスです。  
  
 このオプションを使用する場合、クラスは、データのスレッド セーフの責任を負う必要があります。 さらに、フリー スレッド マーシャラーを集約し、その他のオブジェクトから取得されたインターフェイス ポインターを使用する必要があるオブジェクトは、インターフェイスが正しくマーシャ リングすることを確認する追加の手順になりません。 通常は、グローバル インターフェイス テーブル (GIT) にインターフェイス ポインターを格納してを使用するたびに、GIT からポインターを取得します。 ATL クラスを提供する[CComGITPtr](../atl/reference/ccomgitptr-class.md) GIT で格納されているインターフェイス ポインターを使用するためです。  
  
## <a name="see-also"></a>参照  
 [概念](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [グローバル インターフェイス テーブルを使用する場合](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [プロセス サーバーがスレッド処理の問題](http://msdn.microsoft.com/library/windows/desktop/ms687205)

