<script lang="ts">
	import { Badge, Box, Button, Card, Flex, Group, Image, Stack, Text, Title } from "@svelteuidev/core";
	import type { Project } from "../app";
	import { AiFillGithub } from "svelte-icons-pack/ai";
	import { Icon } from "svelte-icons-pack";
  export let project: Project
</script>

<Card shadow='sm' padding='lg' css>
	<Flex direction="column" justify="space-between" css={{height: "100%"}}>
    <Box>
        <Card.Section first padding='lg' css={{marginBottom: "10px"}}>
          <Image
            src={project.imageSrc}
            height={260}
            alt={project.title}
              usePlaceholder
          />
        </Card.Section>
        <Group css={{marginBottom: "10px"}}>
            {#each project.technologies as technology}
              <Badge color='violet'>
                  {technology}
              </Badge>
            {/each}
        </Group>
        
          <Box css={{marginBottom: "10px"}}>
            <Title order={3} weight={500} css={{marginBottom: "10px"}}>{project.title}</Title>
            <Stack gap={2}>
              {#each project.description as description}
                <Text css={{lineHeight: "1.4"}}>{description}</Text>
              {/each}
            </Stack>
          </Box>
      </Box>
    <Stack gap={4}>
        <Button variant='light' color='green' fullSize  target="_blank" href={project.link} size="lg">
          Open Project
        </Button>
        <Button variant='light' color='blue' fullSize target="_blank" href={project.githubLink} size="lg">
          <Icon src={AiFillGithub} slot="leftIcon" />
          Github Link
        </Button>
      </Stack>
  </Flex>
</Card>

