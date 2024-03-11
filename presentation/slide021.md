           ______                          _ __                                                  ____                           __  __  _
          / ____/___  ____ ___  ____ ___  (_) /_   ____ ___  ___  ______________ _____ ____     / __/___  _________ ___  ____ _/ /_/ /_(_)___  ____ _
         / /   / __ \/ __ `__ \/ __ `__ \/ / __/  / __ `__ \/ _ \/ ___/ ___/ __ `/ __ `/ _ \   / /_/ __ \/ ___/ __ `__ \/ __ `/ __/ __/ / __ \/ __ `/
        / /___/ /_/ / / / / / / / / / / / / /_   / / / / / /  __(__  )__  ) /_/ / /_/ /  __/  / __/ /_/ / /  / / / / / / /_/ / /_/ /_/ / / / / /_/ /
        \____/\____/_/ /_/ /_/_/ /_/ /_/_/\__/  /_/ /_/ /_/\___/____/____/\__,_/\__, /\___/  /_/  \____/_/  /_/ /_/ /_/\__,_/\__/\__/_/_/ /_/\__, /
                                                                               /____/                                                       /____/
        ** Using gqq you can format a line of text. **
        ** Especially useful for commit message body **
        The data pointers for `float3` and `int3` were being cast down to their `const` overloads, so the program silently didn't update the host buffer when the GPU code ran. In this commit, we fix this MISC

















































































slide 021
