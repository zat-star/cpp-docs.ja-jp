---
title: "directory_entry クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
dev_langs: C++
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: f79999e2913bb0058a62f112d4450e89daf456e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="directoryentry-class"></a>directory_entry クラス
`*X` によって返されるオブジェクトを表します。*X* は、[directory_iterator](../standard-library/directory-iterator-class.md) または [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
class directory_entry;  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、[path](../standard-library/path-class.md) 型のオブジェクトを格納します。 格納できる `path` は、[path クラス](../standard-library/path-class.md)のインスタンスまたは `path` の派生型のインスタンスです。 また、2 つの [file_type](../standard-library/filesystem-enumerations.md#file_type) 値も格納します。1 つは格納されたファイル名の状態に関する既知の情報を表し、もう 1 つはファイル名のシンボリック リンクの状態に関する既知の情報を表します。  
  
 詳細およびコード例については、「[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)」をご覧ください。  
  
## <a name="assign"></a>assign  
  
```  
void assign(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 このメンバー関数は、pval を mypath に、stat を mystat に、symstat を mysymstat に割り当てます。  
  
## <a name="directoryentry"></a>directory_entry  
  
```  
directory_entry() = default;  
directory_entry(const directory_entry&) = default;  
directory_entry(directory_entry&&) noexcept = default;  
explicit directory_entry(const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 既定のコンストラクターは想定どおりの動作をします。 4 番目のコンストラクターは、mypath を pval に、mystat を stat_arg に、mysymstat を symstat_arg に初期化します。  
  
## <a name="operator"></a>operator!=  
  
```  
bool operator!=(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は !(*this == right) を返します。  
  
## <a name="operator"></a>operator=  
  
```  
directory_entry& operator=(const directory_entry&) = default;  
directory_entry& operator=(directory_entry&&) noexcept = default;  
```  
  
 この既定のメンバー代入演算子は想定どおりに動作します。  
  
## <a name="operator"></a>operator==  
  
```  
bool operator==(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は mypath == right.mypath を返します。  
  
## <a name="operatorlt"></a>演算子&lt;  
  
```  
bool operator<(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は mypath を返します&lt;right.mypath です。  
  
## <a name="operatorlt"></a>operator&lt;=  
  
```  
bool operator&lt;=(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は !(right \< *this) を返します。  
  
## <a name="operatorgt"></a>演算子&gt;  
  
```  
bool operator&gt;(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数は right \< *this を返します。  
  
## <a name="operatorgt"></a>operator&gt;=  
  
```  
bool operator&gt;=(const directory_entry& right) const noexcept;  
```  
  
 このメンバー関数を返します。(* この\<右)。  
  
## <a name="operator-const-pathtype"></a>operator const path_type&  
  
``` 
 operator const std::experimental::filesystem::path&() const; 
```  
  
 このメンバー演算子は mypath を返します。  
  
## <a name="path"></a>path  
  
```  
const std::experimental::filesystem::path& path() const noexcept;  
```  
  
 このメンバー関数は mypath を返します。  
  
## <a name="replacefilename"></a>replace_filename  
  
```  
void replace_filename(
    const std::experimental::filesystem::path& pval,  
    file_status stat_arg = file_status(),  
    file_status symstat_arg = file_status());
```  
  
 このメンバー関数は、mypath を mypath.parent_path() / pval、mystat を stat_arg、mysymstat を symstat_arg と置き換えます。  
  
## <a name="status"></a>状態  
  
```  
file_status status() const; 
file_status status(error_code& ec) const noexcept;  
```  
  
 メンバー関数はどちらも、恐らく最初に mystat を次のように変更し、それからこれを返します。  
  
1.  status_known(mystat) の場合は何も実行しません。  
  
2.  それ以外の場合は、!status_known(mysymstat) && !is_symlink(mysymstat) であれば mystat = mysymstat です。  
  
## <a name="symlinkstatus"></a>symlink_status  
  
```  
file_status symlink_status() const; 
file_status symlink_status(error_code& ec) const noexcept;  
```  
  
 メンバー関数ではどちらも、恐らく最初に mysymstat を次のように変更し、それからこれを返します。status_known(mysymstat) の場合は何もしません。 それ以外の場合、mysymstat = symlink_status(mypval) です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<実験/filesystem&gt;  
  
 **名前空間:** std::experimental::filesystem  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<ファイル システム&gt;](../standard-library/filesystem.md)

