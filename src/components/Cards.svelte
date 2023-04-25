<script>
    export let c
    import { Modal, Content, Trigger}  from "sv-popup"
</script>

<main>
        <Modal basic big={true}>
            <Content>
                <h1>{c.name}</h1>
                <h5>{c.fortune_telling}</h5>
            </Content> 
            <Trigger>
                <img src="./assets/cards/{c.img}" alt="">
            </Trigger>
        </Modal>
</main>

<style>
   .tarot{
        margin: .5rem;
    }

    img{
        height: 10rem;
    }

    .modal-backdrop {
   background-color: yellow;
}

</style>