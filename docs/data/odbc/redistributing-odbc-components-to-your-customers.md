---
title: "お客様の ODBC コンポーネントの再配布 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC components, redistributing
- ODBC, distributing components
- components [C++], distributing
- ODBC Administrator
- components [C++]
- components [C++], redistributing
ms.assetid: 17b065b4-a307-4b89-99ac-d05831cfab87
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 861eceef234b77b96179c51979cb7d1c0d09eeeb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-odbc-components-to-your-customers"></a>ODBC の構成要素の配布
Odbc データ ソース アドミニストレーターの機能をアプリケーションに組み込む場合必要がありますもファイルを配布するユーザーに、これらのプログラムを実行しています。 これらの ODBC ファイルは、Visual C++ CD-ROM の \OS\System ディレクトリに存在します。 Redistrb.wri ファイルと同じディレクトリに使用許諾契約書は、再配布する ODBC ファイルの一覧を含みます。  
  
 出荷する ODBC ドライバーのマニュアルを参照します。 出荷するには、Dll とその他のファイルを確認する必要があります。 参照する必要がありますも[ODBC の構成要素を顧客に](../../data/odbc/redistributing-odbc-components-to-your-customers.md)、ODBC コンポーネントを再配布する方法について説明しています。  
  
 さらに、ほとんどの場合にその他の 1 つのファイルを含める必要があります。 Odbccr32.dll は、ODBC カーソル ライブラリです。 このライブラリは、前方と後方スクロールの機能レベル 1 のドライバーを使用します。 スナップショットのサポートの機能も提供します。 ODBC カーソル ライブラリの詳細については、次を参照してください。 [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)です。  
  
 次のトピックでは、データベース クラスと ODBC を使用してについて詳しく説明します。  
  
-   [ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)  
  
-   [ODBC: ODBC データ ソースの設定](../../data/odbc/odbc-configuring-an-odbc-data-source.md)  
  
-   [ODBC: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)  
  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)   
 [ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)