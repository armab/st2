__defaults__(
    {(python_test, python_tests): dict(tags=["unit"])},
    extend=True,
)

python_tests(
    name="tests",
    dependencies=[
        # several files import tests.unit.base which is ambiguous. Tell pants which one to use.
        "st2common/tests/unit/base.py",
    ],
    uses=["mongo", "rabbitmq"],
    overrides={
        "test_util_file_system.py": dict(
            dependencies=[
                "st2tests/st2tests/policies",
                "st2tests/st2tests/policies/meta",
            ],
        ),
    },
)

python_test_utils(
    sources=["*.py", "!test_*.py"],
)
