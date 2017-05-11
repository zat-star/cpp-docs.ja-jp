---
title: "filesystem_error クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 87ae0515eba774f73ee0d4283a020ce27c3fbe6f
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="filesystemerror-class"></a>filesystem_error クラス
低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class filesystem_error    : public system_error;  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、\<filesystem> 関数のエラーを報告するためにスローされる例外すべてに対する基底クラスとして機能します。 このクラスは、文字列型のオブジェクトを格納します。ここでは説明をわかりやすくするために、このオブジェクトを mymesg と呼ぶことにします。 さらに、このクラスは path 型のオブジェクトを 2 つ格納します。ここでは、これらのオブジェクトを mypval1 および mypval2 と呼ぶことにします。  
  
## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error  
  
```  
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    const path& pval2,
    error_code ec);
```  
  
 最初のコンストラクターは、what_arg と ec からメッセージを構築します。 2 番目のコンストラクターは、mypval1 に格納するメッセージを pval1 から構築します。 3 番目のコンストラクターは、mypval1 に格納するメッセージを pval1 から構築して、mypval2 に格納するメッセージを pval2 から構築します。  
  
## <a name="filesystemerrorpath1"></a>filesystem_error::path1  
  
```  
const path& path1() const noexcept;  
```  
  
 このメンバー関数は、mypval1 を返します。  
  
## <a name="filesystemerrorpath2"></a>filesystem_error::path2  
  
```  
const path& path2() const noexcept;  
```  
  
 このメンバー関数は、mypval2 を返します。  
  
## <a name="filesystemerrorwhat"></a>filesystem_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 このメンバー関数は、NTBS へのポインターを返します。この NTBS は、可能であればruntime_error::what()、system_error::what()、mymesg、mypval1.native_string()、および mypval2.native_string() から構成されます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<filesystem >  
  
 **名前空間:** std::experimental::filesystem  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [system_error クラス](../standard-library/system-error-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [\<exception>](../standard-library/exception.md)


