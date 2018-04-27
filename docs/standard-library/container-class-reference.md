---
title: コンテナー クラス::reference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca6cfbd219f8184194e155c4223453ed510ba6a5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="container-classreference"></a>コンテナー クラス::reference

> [!NOTE]
> このトピックは、C++ 標準ライブラリで使用されるコンテナーの例 (実際には機能しない) として、Visual C++ ドキュメントに含まれています。 詳細については、「[C++ Standard Library Containers (C++ 標準ライブラリ コンテナ―)](../standard-library/stl-containers.md)」をご覧ください。

被制御シーケンスの要素への参照として使用できるオブジェクトを表します。

## <a name="syntax"></a>構文

```

typedef T2 reference;
```

## <a name="remarks"></a>コメント

ここでは、指定されていない型 **T2** のシノニムとして記述されています (通常は **Alloc::reference**)。 **reference** 型のオブジェクトは、[const_reference](../standard-library/container-class-const-reference.md) 型のオブジェクトにキャストできます。

## <a name="see-also"></a>関連項目

[サンプル コンテナー クラス](../standard-library/sample-container-class.md)<br/>
