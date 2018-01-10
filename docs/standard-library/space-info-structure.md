---
title: "space_info 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::tr2::sys::space_info
dev_langs: C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50657e33becd0fb2dae94d515f82120d6a71e342
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="spaceinfo-structure"></a>space_info 構造体
ボリュームに関する情報を保持します。  
  
## <a name="syntax"></a>構文  
  
```  
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`unsigned long long available`|ボリューム上のデータを表すために使用できるバイト数を表します。|  
|`unsigned long long capacity`|ボリュームを表すことのできるバイト数の合計数を表します。|  
|`unsigned long long free`|ボリューム上のデータを表すために使用されないバイト数を表します。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<filesystem >  
  
 **名前空間:** std::experimental::filesystem  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [領域](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)

