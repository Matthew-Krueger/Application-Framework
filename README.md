# Application-Framework
A Simple Application framework for building applications and managing their lifecycle.

To use, do this in the TU where you want your main to be hosted. 
```
#define APP_FW_INCLUDE_MAIN
#include "AppFramework/MainCreator.hpp"
```

And do this to define your class. Implement the methods.

```
#include "AppFramework/AppFramework.hpp"

namespace MyNamespace{

    class MyApp : public AppFramework::Application{
    public:
        MyApp();
        virtual ~MyApp();

        virtual int run() override;
        
        inline static MyApp& get(){return *(MyApp*)s_Instance; };

    };

}
```

In your constructor, set the singleton instance by calling this method:
```
    setInstance();
```

Lastly, Implement this function which creates an instance of the application you created
```
AppFramework::Application* AppFramework::createApplication(){

    return new MyNamespace::MyApp();

}
```