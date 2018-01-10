---
title: "文字の利点の移植性の設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 554137352c0a8f7275a051e4026020fce25edbb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="benefits-of-character-set-portability"></a>文字セットにおける移植性の利点
現在しないアプリケーションの国際化する場合でも、MFC および C ランタイムの移植性の機能を使用する利点が得られます。  
  
-   柔軟な基本コードは、移植可能な方法でコーディングします。 後で移動できます簡単に Unicode や MBCS にします。  
  
-   Unicode を使用すると、Windows 2000 の場合、アプリケーションはより効率的です。 Windows 2000 では、Unicode を使用するためと、オペレーティング システムから渡される Unicode 以外の文字列変換される必要が、オーバーヘッドが発生します。  
  
-   MBCS を使用するには、Windows 95 などの Windows 2000 または Windows 98 以外のプラットフォームで Win32 国際市場をサポートすることができます。  
  
## <a name="see-also"></a>参照  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [Unicode のサポート](../text/support-for-unicode.md)