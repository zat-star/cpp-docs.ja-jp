---
title: "ODBC とデータベース クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- database classes [C++], ODBC
- ODBC API functions [C++]
- ODBC classes [C++], MFC database classes
- MFC [C++], ODBC and
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cf4d5dae14a59cc8b4c6d17ff118cdde59c28af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="odbc-and-the-database-classes"></a>ODBC とデータベース クラス
MFC ODBC データベース クラスは、通常行う自分で、メンバー内の関数、ODBC API 関数呼び出しをカプセル化する、 [CDatabase](../../mfc/reference/cdatabase-class.md)と[CRecordset](../../mfc/reference/crecordset-class.md)クラスです。 たとえば、複雑な odbc 呼び出し、記憶域の場所、エラー状態の処理およびその他の操作に返されるレコードのバインドは管理するデータベース クラスでされます。 その結果、かなりシンプルなインターフェイスとクラスを使用して、レコード セット オブジェクトを使用してレコードを操作します。  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。  
  
 データベース クラスには、ODBC の機能がカプセル化が ODBC API 関数の 1 対 1 のマッピングは提供しません。 データベース クラスより高度な抽象化、データ アクセス オブジェクトは、Microsoft Access や Microsoft Visual Basic で見つかったとしてモデル化を提供します。 詳細については、次を参照してください。 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)