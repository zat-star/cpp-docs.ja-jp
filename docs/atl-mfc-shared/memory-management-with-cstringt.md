---
title: "CStringT によるメモリ管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs: C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbf623344ec52abce28a08670e7f3cd09140563b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-with-cstringt"></a>CStringT によるメモリ管理
クラス[CStringT](../atl-mfc-shared/reference/cstringt-class.md)は可変長文字列の操作に使用されるテンプレート クラス。 これらの文字列を保持するためにメモリが割り当てられの各インスタンスに関連付けられている文字列マネージャー オブジェクトを介してリリース`CStringT`です。 MFC と ATL の既定のインスタンス化を提供します。`CStringT`という`CString`、 `CStringA`、および`CStringW`、別の文字型の文字列を操作します。 これらの文字型は型**TCHAR**、 `char`、および`wchar_t`、それぞれします。 これらの既定の文字列型では、(ATL) でプロセス ヒープまたは (MFC) では、CRT ヒープからメモリを割り当てる文字列マネージャーを使用します。 一般的なアプリケーションは、このメモリの割り当て方法で十分です。 ただし、処理を要するを行うコードの文字列 (マルチ スレッド コード) の既定のメモリ マネージャーが適切に機能しない可能性がありますを使用します。 このトピックの既定のメモリ管理動作をオーバーライドする方法について説明`CStringT`、当面のタスク用に最適化されたアロケーターを具体的に作成します。  
  
-   [カスタム文字列マネージャーの実装 (基本方法)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [ヒープ競合の回避](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [カスタム文字列マネージャーの実装 (詳細方法)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: 例のカスタム文字列マネージャー](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>参照  
 [CustomString サンプル](../visual-cpp-samples.md)

