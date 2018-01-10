---
title: "ODBC クラスおよびスレッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC classes, and threads
- ODBC, multithreaded applications
- threading [MFC], ODBC support
ms.assetid: 16543926-7331-41a6-ba50-72288f2a61b7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d1d922dfc34fa3e5530eca77a6501ad3e331fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="odbc-classes-and-threads"></a>ODBC クラスおよびスレッド
MFC ODBC クラスのマルチ スレッドのサポートは MFC 4.2 以降ではです。 ただし、MFC DAO クラスのマルチ スレッドのサポートが提供されないことに注意してください。  
  
 ODBC クラスには、マルチ スレッドのサポートには、いくつかの制限があります。 これらのクラスには、ODBC API をラップするため、ビルドされたコンポーネントのマルチ スレッドのサポートに制限されます。 たとえば、多くの ODBC ドライバーはスレッド セーフです。そのため、MFC ODBC クラスは、これらのドライバーのいずれかで使用する場合のスレッド セーフではできません。 特定のドライバーは、スレッド セーフであるかどうかを確認する必要があります。  
  
 マルチ スレッド アプリケーションを作成するときに、複数のスレッドを使用して、同じオブジェクトを操作するには十分に注意してください。 たとえば、同じを使用して`CRecordset`データを取得するときに、2 つのスレッド内のオブジェクトの問題が発生する以外の場合は 1 つのスレッドでのフェッチ操作は、その他のスレッドにフェッチされるデータを上書き可能性があります。 個別のスレッドで、MFC ODBC クラスの一般的な使用方法は、開いているを共有する`CDatabase`を個別に、同じ ODBC 接続を使用するスレッド間でオブジェクト`CRecordset`各スレッドでのオブジェクト。 開かれていない必要があります渡さないことに注意してください`CDatabase`オブジェクトを`CRecordset`別のスレッド内のオブジェクト。  
  
> [!NOTE]
>  複数のスレッドが同じオブジェクトを操作が必要な場合は、クリティカル セクションなど、適切な同期機構を実装する必要があります。 注意して、その特定の操作など**開く**、保護されていません。 これらの操作は呼び出されません同時に複数のスレッドからことを確認しておく必要があります。  
  
 マルチ スレッド アプリケーションの作成の詳細については、次を参照してください。[マルチ スレッド トピック](../../parallel/multithreading-support-for-older-code-visual-cpp.md)です。  
  
## <a name="see-also"></a>参照  
 [Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [データ アクセス プログラミング (MFC/ATL)](../../data/data-access-programming-mfc-atl.md)