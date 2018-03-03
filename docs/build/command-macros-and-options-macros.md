---
title: "コマンド マクロおよびオプション マクロ |Microsoft ドキュメント"
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
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06f5d48395c0395a85c90096bf2dbad8627ac41a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="command-macros-and-options-macros"></a>コマンド マクロとオプション マクロ
コマンド マクロは Microsoft 製品の定義済みです。 オプション マクロは、これらの製品にオプションを表し、既定では未定義です。 両方定義済みの推論規則で使用され、記述ブロックまたはユーザー定義の推論規則で使用できます。 コマンド マクロは、オプションを含むコマンドラインの一部またはすべてを表す再定義することができます。 オプション マクロは、左の未定義の場合、null 文字列を生成します。  
  
|Microsoft の製品|コマンド マクロ|として定義されています。|オプション マクロ|  
|-----------------------|-------------------|----------------|-------------------|  
|マクロ アセンブラー|**AS**|ml|**AFLAGS**|  
|基本的なコンパイラ|**ビジネス継続性**|ビジネス継続性|**BFLAGS**|  
|C コンパイラ|**[CC]**|cl|**CFLAGS**|  
|C++ コンパイラ|**CPP**|cl|**CPPFLAGS**|  
|C++ コンパイラ|**CXX であります。**|cl|**ように**|  
|Resource Compiler|**RC**|rc|**RFLAGS**|  
  
## <a name="see-also"></a>参照  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)