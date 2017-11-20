---
title: operator== (&lt;sample container&gt;) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
dev_langs: C++
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c42f6328ce7867c49e240bbcd5946e551b2a5ac6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;sample container&gt;)
> [!NOTE]
>  このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。  
  
 `operator==` をオーバーロードしてテンプレート クラス [Container](../standard-library/sample-container-class.md) の 2 つのオブジェクトを比較します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
bool operator==(
    const Container <Ty>& left,  
    const Container <Ty>& right);
```  
  
## <a name="return-value"></a>戻り値  
 返します`left.`[サイズ](../standard-library/container-class-size.md) ` == right.size && equal(left.`[開始](../standard-library/container-class-begin.md)`, left.`[終了](../standard-library/container-class-end.md)`, right.begin)`です。  
  
## <a name="see-also"></a>関連項目  
 [\<sample container>](../standard-library/sample-container.md)

