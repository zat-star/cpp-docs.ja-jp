---
title: "スレッド モデルと重要なセクション クラス (ATL) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.atl.threads.models
dev_langs:
- C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1501fe4f761b9bc8775018d6566ceff5fb0aa477
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="threading-models-and-critical-sections-classes"></a>スレッド モデルと重要なセクション クラス
次のクラスを定義、スレッド処理モデルと重要なセクション。  
  
-   [残さ](../atl/reference/catlautothreadmodule-class.md)スレッド プール、アパートメント モデルの COM サーバーを実装します。  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md)スレッド プール、アパートメント モデルの COM サーバーを実装するためのメソッドを提供します。  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md)変数をインクリメントおよびデクリメントのスレッド セーフであるメソッドを提供します。 クリティカル セクションを提供します。  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md)変数をインクリメントおよびデクリメントのスレッド セーフであるメソッドを提供します。 クリティカル セクションは提供されません。  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md)変数をインクリメントおよびデクリメントするためのメソッドを提供します。 クリティカル セクションは提供されません。  
  
-   [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) 1 つのオブジェクト クラスに対して適切なスレッド処理モデル クラスを決定します。  
  
-   [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel)はグローバルに使用できるオブジェクトに対して適切なスレッド処理モデル クラスを決定します。  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md)を取得し、クリティカル セクションを解放するためのメソッドが含まれます。 クリティカル セクションが自動的に初期化します。  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md)を取得し、クリティカル セクションを解放するためのメソッドが含まれます。 クリティカル セクションは、明示的に初期化する必要があります。  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md)内のメソッドをミラー化`CComCriticalSection`クリティカル セクションを指定しなくてもします。 メソッドは、`CComFakeCriticalSection`何もしません。  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) CRT スレッドの作成機能を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Windows スレッドの作成機能を提供します。 スレッド CRT 関数を使用しない場合は、このクラスを使用します。  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../atl/atl-class-overview.md)

