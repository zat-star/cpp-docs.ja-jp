---
title: "文字の利点の移植性の設定 |Microsoft ドキュメント"
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
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ce02fa834c39f629990d4f3c9785de94bd02196
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="benefits-of-character-set-portability"></a>文字セットにおける移植性の利点
現在しないアプリケーションの国際化する場合でも、MFC および C ランタイムの移植性の機能を使用する利点が得られます。  
  
-   柔軟な基本コードは、移植可能な方法でコーディングします。 後で移動できます簡単に Unicode や MBCS にします。  
  
-   Unicode を使用すると、Windows アプリケーションはより効率的です。 Windows では、Unicode を使用するためと、オペレーティング システムから渡される Unicode 以外の文字列変換される必要が、オーバーヘッドが発生します。  

  
## <a name="see-also"></a>参照  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [Unicode のサポート](../text/support-for-unicode.md)