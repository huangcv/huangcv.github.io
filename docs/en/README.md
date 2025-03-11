# My Docsify Server.English

```java
public class HelloWorld {
    
}
```
$$
\int_{a}^{b} x^2 dx
$$

```cpp
#ifndef CYBERDOG_BMS__BMS_BASE_HPP_
#define CYBERDOG_BMS__BMS_BASE_HPP_

#include <string>
#include <memory>
#include "rclcpp/rclcpp.hpp"
#include "protocol/srv/led_execute.hpp"
#include "protocol/msg/bms_status.hpp"
#include "protocol/srv/bms_cmd.hpp"

namespace cyberdog
{
namespace device
{

class BMSBase
{
public:
  using BmsStatusMsg = protocol::msg::BmsStatus;

  virtual bool Config() = 0;
  virtual bool Init(
    std::function<void(BmsStatusMsg)> function_callback,
    bool simulation = false) = 0;
  virtual int32_t SelfCheck() = 0;
  virtual bool RegisterTopic(std::function<void(BmsStatusMsg)> function_callback) = 0;
  virtual void ServiceCommand(
    const std::shared_ptr<protocol::srv::BmsCmd::Request> request,
    std::shared_ptr<protocol::srv::BmsCmd::Response> response) = 0;
  virtual bool LowPower() = 0;

protected:
  BMSBase() {}
};  // class BMSBase
}  // namespace device
}  // namespace cyberdog

#endif  // CYBERDOG_BMS__BMS_BASE_HPP_

```

```python
from pyecharts import options as opts
from pyecharts.charts import BMap
from pyecharts.faker import Faker

c = (
    BMap()
    .add_schema(baidu_ak="FAKE_AK", center=[120.13066322374, 30.240018034923])
    .add(
        "bmap",
        [list(z) for z in zip(Faker.provinces, Faker.values())],
        label_opts=opts.LabelOpts(formatter="{b}"),
    )
    .set_global_opts(title_opts=opts.TitleOpts(title="BMap-基本示例"))
    .render("bmap_base.html")
)
```

```bash
ros2 launch camera_test stereo_camera.py

#查看name space
ros2 node list 

###如果是开机自启，注意topic前加上命名空间

ros2 lifecycle set /stereo_camera configure

ros2 lifecycle set /stereo_camera activate


ros2 lifecycle set /stereo_camera deactivate

ros2 lifecycle set /stereo_camera cleanup
```

> 1. sdfasdfsdfsdfsafsdf
> 2. sdjfskdlafjksdlfjsdlkfjlskdjfksldf