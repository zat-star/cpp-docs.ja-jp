---
title: "setjmp longjump |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 744b855d1b867507b54973f17e2a4f98b63e2b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setjmplongjump"></a>setjmp/longjump
Setjmpex.h または setjmp.h を含めると、すべての呼び出し[setjmp](../c-runtime-library/reference/setjmp.md)または[longjmp](../c-runtime-library/reference/longjmp.md)デストラクターを呼び出すし、最後に呼び出されをアンワインドが発生します。  これは、プロセスは、finally 句の setjmp.h とデストラクターを呼び出さない x86 とは異なります。  
  
 呼び出し`setjmp`現在のスタック ポインター、非 volatile レジスタと MxCsr レジスタに保持されます。  呼び出す`longjmp`、一番最近に戻る`setjmp`呼び出しサイトのリセット、スタック ポインター、非 volatile レジスタと MxCsr レジスタ、状態に戻すように、最新では保持されます`setjmp`呼び出します。  
  
## <a name="see-also"></a>参照  
 [呼び出し規則](../build/calling-convention.md)