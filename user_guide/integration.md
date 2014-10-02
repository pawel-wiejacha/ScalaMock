# Integration with testing frameworks

ScalaMock can be used in tests written using ScalaTest and Specs2 frameworks.

## ScalaTest 

To provide mocking support in ScalaTest suites just mix your suite with `org.scalamock.scalatest.MockFactory`

```scala
import org.scalatest.FlatSpec
import org.scalatest.ShouldMatchers
import org.scalamock.scalatest.MockFactory

class CoffeeMachineTest extends FlatSpec with ShouldMatchers with MockFactory {

  "CoffeeMachine" should "not turn on the heater when the water container is empty" in {
      val waterContainerMock = mock[WaterContainer]
      (waterContainerMock.isEmpty _).expects().returning(true)
      // ...
  }
}
```

## Specs2

To use ScalaMock in Specs2 tests you should run each test case in separate fixture context that implements `org.scalamock.specs2.MockContext`


```scala
import org.specs2.mutable.Specification
import org.scalamock.specs2.MockContext

class BasicCoffeeMachineTest extends Specification {

	"CoffeeMachine" should {
	     "not turn on the heater when the water container is empty" in new MockContext {
	         val waterContainerMock = mock[WaterContainer]
	         (waterContainerMock.isOverfull _).expects().returning(true)
	         // ...
	     }
	}
}
```
There are other ways of using ScalaMock in Specs2 tests - please check [Sharing mocks and expectations](/sharing_mocks) chapter for more details.

