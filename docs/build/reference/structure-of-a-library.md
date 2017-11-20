---
title: "ライブラリの構造 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 875dddb961b18378029de08582e728ad626be948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="structure-of-a-library"></a>ライブラリの構造
ライブラリには、COFF オブジェクトが含まれています。 オブジェクトをライブラリには、関数とプログラムの他のオブジェクトで外部から参照可能なデータを含めます。 ライブラリ内のオブジェクトは、ライブラリのメンバーとも呼ばれます。  
  
 /LINKERMEMBER オプションを使用して、DUMPBIN ツールを実行して、ライブラリの内容に関する追加情報を取得できます。 詳細については、このオプションは、次を参照してください。 [DUMPBIN リファレンス](../../build/reference/dumpbin-reference.md)です。  
  
## <a name="see-also"></a>関連項目  
 [LIB の概要](../../build/reference/overview-of-lib.md)