<script >
    import { Button, Card } from "attractions";
    export let name;
    export let email;
</script>


<div class= "some">
    <Card outline>
        <h3 style="color: red;">De Anza</h3>
        <a href="./{name}">
            <Button>
                <h2>Event calendar</h2>
            </Button>
        </a>
        <a href="./{name}/articles">
            <Button>
                <h2>Meeting notes</h2>
            </Button>
        </a>
        <a href="https://mail.google.com/mail/?view=cm&fs=1&to={email}&su=question&body=BODY">
            <Button>
                <h2>Ask questions</h2>
            </Button>
        </a>
    </Card>
</div>

<style>
    .some {
        width: 300px;
        padding: 20px;
        position: absolute;
    }
    .used {
        max-width: 300px;
    }
    h3{
        font-size: 1.5em;
    }
    h2{
        font-size: 1em;
    }

</style>