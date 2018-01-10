---
title: "スナップショット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC cursor library [ODBC], snapshots
- cursors [ODBC], static
- recordsets, snapshots
- snapshots, support in ODBC
- static cursors
- ODBC recordsets, snapshots
- cursor library [ODBC], snapshots
- snapshots
ms.assetid: b5293a52-0657-43e9-bd71-fe3785b21c7e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c31e08fdda3cef526f46946e45ef956f9ad1adaa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="snapshot"></a>スナップショット
スナップショットは、スナップショットの作成時に存在していたデータの静的なビューを反映するレコード セットです。 スナップショットを開くすべてのレコードに移動すると、レコードのセットが含まれているし、呼び出すことにより、スナップショットを再構築するまでの値を変更しないで**Requery**です。  
  
> [!NOTE]
>  このトピックの内容は、MFC ODBC クラスに該当します。 MFC ODBC クラスではなく、MFC DAO クラスを使用する場合は、次を参照してください。 [cdaorecordset::open](../../mfc/reference/cdaorecordset-class.md#open)スナップショット タイプのレコード セットの詳細についてはします。  
  
 データベース クラスと、更新可能または読み取り専用のスナップショットを作成できます。 ダイナセットとは異なり、更新可能なスナップショットは他のユーザーによるレコードへの変更が反映されませんが、更新と、プログラムによる削除は反映します。 スナップショットに追加されたレコードに呼び出されるまでスナップショットに表示されるならない**Requery**です。  
  
> [!TIP]
>  スナップショットは、ODBC の静的カーソルです。 静的カーソルは実際は、1 行のデータにそのレコードをスクロールするまでです。 すべてのレコードを直ちに取得するためには、レコード セットの末尾までスクロールし、し、スクロールを表示する最初のレコードをできます。 ただし、こと、最後にスクロールするためのオーバーヘッドし、パフォーマンスを下げることができます。  
  
 スナップショットは、データとレポートを生成するか計算を実行すると、操作中に固定しておく必要がある場合に最も役に立ちます。 そうであっても、データ ソースできます食い違って、スナップショットから、随時を再構築することができます。  
  
 スナップショットのサポートは、静的カーソルを提供し、位置指定のレベル 1 のドライバーの更新 (updateability に必要)、ODBC カーソル ライブラリに基づいています。 カーソル ライブラリ DLL は、このサポートのメモリに読み込む必要があります。 構築する場合、`CDatabase`オブジェクト呼び出しとその`OpenEx`メンバー関数を指定してください、**読み込む**のオプション、`dwOptions`パラメーター。 呼び出す場合は、**開く**メンバー関数の場合、カーソル ライブラリは既定で読み込まれます。 ダイナセットを使う場合のスナップショットではなくを使用している場合、カーソル ライブラリが読み込まれるをたくないです。  
  
 スナップショットはときに、ODBC カーソル ライブラリが読み込まれた場合にのみ使用可能な`CDatabase`オブジェクトが構築または使用している ODBC ドライバーは、静的カーソルをサポートしています。  
  
> [!NOTE]
>  一部の ODBC ドライバー (静的カーソル) のスナップショットを更新できない可能性があります。 サポートされているカーソルは、ドライバーのドキュメントとサポートされる同時実行の種類を確認してください。 確実に更新可能なスナップショットを作成するときにメモリに、カーソル ライブラリを読み込むことを確認してください、`CDatabase`オブジェクト。 詳細については、次を参照してください。 [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)です。  
  
> [!NOTE]
>  スナップショットとダイナセットを使う場合の両方を使用する場合は、する必要があります基づかせる 2 つの異なる`CDatabase`オブジェクト (2 つの異なる接続)。  
  
 すべてのレコードのプロパティのスナップショット共有の詳細については、次を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)です。 ODBC と ODBC カーソル ライブラリを含む、スナップショットの詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)です。  
  
## <a name="see-also"></a>参照  
 [ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)